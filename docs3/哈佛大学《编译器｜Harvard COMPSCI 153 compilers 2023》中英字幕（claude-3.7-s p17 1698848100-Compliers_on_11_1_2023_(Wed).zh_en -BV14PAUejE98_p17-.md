# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p17 1698848100-Compliers_on_11_1_2023_(Wed).zh_en -BV14PAUejE98_p17-

Welcome， everyone。don'tSo get started。No new announcements， relevant information of course。

 but this is things you've all seen。 please fill in the homework 3 survey。

 we've gotten about two thirds of the class so far that have done that talking about the experience in homework 3。

You can look for the link。 You can look on the P DF slides that are on the canvas website or the email that I sent about a week and a half ago。

Homework 4， I know many of you are working on that that is due on Monday， so five days away。

 you can of course use the standard up to three days worth of late minutes for that。

We'll be handing back homework three pretty soon that was due。嗯。

How long has it been since you entered in Homeoke 3？A was you on Wednesday， right？A Wednesday。

 a Monday， a Monday。 Okay， so we're almost at the 10 days。 Don't worry， we will get it back。

 It should be later this afternoon。嗯。The embedded ethics homework is due today。

 No late minutes on that one。 So please get that in by 1159 tonight。

And then homework 5 will be released on Monday， I'll be talking a little bit about homeworkwork Five today and also go through some of the handout information in more detail in Monday's lecture。



![](img/5ab24c3086ef056c29825f3b3e5bf0f4_1.png)

But really， the stuff we're covering today continues to be relevant to homeworkoke  five。

Any questions on the admin side of things。Okay。🤧嗯。So last class。

 we introduced kind of the key idea of type checking， right this idea， that type checking。

 the types are an approximation of the computation that's going to happen。 and moreover。

 that we can essentially have。A function that takes in an AST and then essentially returns successfully if the program type checks。

And the idea of type soundness that if a program type checks， if this function says yes。

 this program is okay， then the program is actually going to be free of certain kinds of runtime errors when you execute the program。

So in today's class， we're going to be。First of all。

 taking a quick look at how we can think about typing in the Ot programming language。

And we'll kind of also do that in a bit more detail on Monday's class as well。嗯。

Talk about how we can take this idea of a。Typing judgment， if you will， of this kind of inference。

 And it's a really powerful idea， one that we can actually extend to thinking about compilation itself。

😊，As a kind of judgment with inference rules that have a very natural sort of implementation。

 that is the search for a proof tree in these inference rules corresponds to the recursive compilation process。

That you' were implementing。Were they going to kind of revisit？Types。

 I mentioned them as thinking about them as an approximation to the computation。

 we can also think about them as a set of values， and that gives rise to a notion of subtyping that is interesting and important。

O。But first， moving on to O。嗯。For Homework 5， a key part of what you'll be doing is adding type checking to Ot。

嗯。They'll be adding in some other language features as well， such asstructs。

 but the key thing is really going to be about type checking。So for Homework5。

 we're going to release in part of the documentation， a type system。

 it's going to be a bit different from the type system that we handed out in Home 4 which was kind of just to give a clear idea about the intended semantics vote。

 the type system for Home5 is going to be a little more sophisticated and the one that you're expected to implement。

But some of the key things that the O type system is going to need to handle is。Imperative update。

So it's not going to quite be like the type system for our MLL， sorry， our Ocal like language， right。

 which you know once a variable was created， it was fixed for the entirety of the scope of the variable。

 white contrast in an imperative language like ot。Java， Python， CC plus plus。

 these variables can be modified during execution， so our type system will need to allow for that。

O also has a distinction between statements and expressions。

Whereas in our functional programming language that we've been looking at。

 everything is an expression。The distinction between statements and expressions is typically that。

Statements can modify things。Stments end up assigning into variables。

 statements might be control flow constructs like wild statements， if statements and so on。

 by contrast， expressions are typically computing things without side effects。

It's not quite true when an expression could invoke a function and the function might do stuff。

 but this distinction between expressions and statements turned out to be useful。Oat， as you know。

 has complicated control flow， right， We have wild loops， four loops。

If we have return statements that can return from a function。

 So part of what we'll be looking at in the homework 5 type system is to make sure， for example。

 that every function returns appropriately。Which I know there's been some discussion on in Ed。

We also have global variables and local variables， and we also have functions that are going to be declared by the programmer and your programme is going to be able to use those functions that have been declared there's also some built in functions。

That Oats able to use。 So how do we make sense of this in the type system？So， I'm going to go。

As I said， just briefly over some of the ideas that are iniated and the relatively simple type system we released in the homework for documentation。

And on Monday， we'll take more of a look at their homework five type system and talk about it。

But some of the key things that are going on with the judgments for the O type system。

Is that instead of having a single environment E of variables that are in scope。

 we're actually going to divide that environment into two pieces。

 the global variables and the local variables。And so when we have our judgments， such as this one。

 that expression E has type T。呃。With our。Environment's going to have these two pieces on the left hand side of this turnstyle。

 the sideways perpendicular sign。G for the。Global variables， L for the local variables。Okay。

 so this is one of the judgments that we're going to have。

And we'll take a look in just a moment and see some of the inference rules for it in the homework for handout。

I mentioned that we have this distinction between expressions and statements。

 So in addition to having this judgment for an expression being well typed。

 we'll have a separate judgment for a statement being well typed。Now。

 a statement doesn't directly evaluate to a value。 So we don't need to indicate the type。

Of a statement。Instead， our judgment for a statement is essentially going to be saying。

This statement is okay， right， The statement is well typed。 it does an appropriate thing。嗯。

The judgment we're going to be using is the following。On the left hand side of the turnst is G。

 the global variables。L， the local variables， and RT， the return type。

Of the function that the statement belongs in。So one of the things that we can check is if the statement returns a value。

Then it returns a value of the appropriate type。One of the interesting things about statements is they don't evaluate to evaluate themselves。

 So we don't need to assign a type。Two S。But part of what statements can do is introduce new local variables。

And so as a result， in our judgment， we're actually going to have。L Prime here。

 the new local context after S executes。And this is going to allow us。To have。

This is going to allow us to have statements that introduce variables and have those variables in the local context in the scope for subsequent statements。

Okay， so let me jump to。Oat documentation that we handed out。Okay。

 so here isode version1 language spec， the grammar。

 which you're all intimately familiar with as you've implemented the rest of the lectureer in the PAsza。

But let's scroll down this document。And take a look at some of the typing rules。嗯。

Here is the judgment that we just talked about under global context G。Local context L expression。

EXP has type T。Here are all of the inference rules for expressions going over onto to the next page as well。

So to see an example of that， if x is a local variable， that is if Xt is in the local context。

The expression X has type T。诶。If x is not a local variable but x is a global variable then and x has type T in the global environment。

 x has type the expression X has type T。 So these two rules together kind of say local variable have priority right if the local environment has the same name as the global environment and you refer to a variable name it should resolve to the local one。



![](img/5ab24c3086ef056c29825f3b3e5bf0f4_3.png)

First。Integer constants have type int， string constants have type string。诶。

The various for reference types， nu null takes a type annotation， which indicates the type of null。

Let's find to。Interesting one。In here。Bary operations。 So if。

Here is another judgment that just indicates the type of a binary operation。

So if we had say seven plus x。Right。Plus is the binary operation， the judgment up here。

Is indicating the type of that， so the plus operation is。Takes two integers， to an int。And down here。

T1 would be instantated with int。 T2 would be instantiateated with int。

 So we need both X1 and X2 to be integers。And the result of the addition would be an integer。切。

Let's scroll on down and take a look at statement rules。 So this is the judgment we talked about。

And the global environment G， local。Environment L1 return type Rrit TY。

The statement is well typed and produces local context， local environment L2。

So let's take a look at some of these。Here's an assignment。So assigning a variable。

Or some kind of tank。嗯。So here we need to type check that the variable we're typing has the appropriate type。

 the expression we're assigning into it has the appropriate type。And in that case。

 the assignment is well formed and it doesn't modify the local context。

the L on the left hand side of the turnst and the right hand side of the judgment is the same。

Here's a return。If we're returning an expression here。

The expression we're returning has to be of type T where T is the return type of the function。

 So this makes sure that if the function says it's returning an int。

We don't mistakenly return a string。This type system doesn't。

Ensure that every function returns appropriately。So in this type system。

 there are programs that are syntactically well formed that won't behave correctly that the type system doesn't rule out。

But we'll see in the homework five type system， which is more sophisticated that it will enforce that。

 that every function returns appropriately。嗯。Here is a variable declaration statement。

So this might be declaring a local variable。 we can check。The syntax of V decal， see what's going on。

But interestingly， we're actually using a different judgment here。

To reason about adding a new variable declaration into the context。

 So we need to scroll up in the document。To see the judgment for adding。A variable declaration。

I had in that check to make sure that the variable is not currently in the local environment。

So we can't shadow the names of any local variables。

 it checks to make sure that the initial value is of the appropriate type T。

And then it adds x of T T into the local context。Let's just take a look at one more rule。

 let's see an if statement。If expression， the expression has to be boolean。嗯。Then block one。

 else block 2。So here in the premises， we're checking block1 and block2 well typed blocks。

 This is again， another judgment， this one here that a block is well typed。嗯。

And we see here that a block。Begins with an open。Curly brace ends with a closed curly brace and has a sequence of statements。

The type checking for a sequence of statements is itself another judgment。Defined here。

And that essentially just checks that each statement in turn is well formed and it threads the local context through。

Mean that if one statement introduces a variable， their variable is going to be available in the rest of the block。

Now， if we go back and look at the if rule， you'll see that just by nature of the premises and the conclusion。

The local environment after the if statement is the same as the local environment before the if statement。

So kind of what that means is any local variables that were introduced in the F branch or the else branch。

Their scope ends at the end of that block。Right， at the end of that of statement。

So these are all kind of subtle things about the nature of the language， the scope of variables。

 whether or not verbal shadowing is allowed。 So many。

 many subtle things going on in the design of this language， but they're expressed。

Sucinctly and unambiguously in these inference rules。And moreover， as you might， as when you。

 when it comes time to implement the type system in the homework 5。

This way of expressing the inference rules actually lends itself pretty naturally。To implementation。

 your implementation will end up reflecting this。 This is， for the most part。

Just recursing on the syntactic structure of the program to check a well statement。

 you'll be checking the guard and you'll be checking the body of the well statement and so on so you can be recursing smaller and smaller so you can imagine the kind of recursive functions that you'd be writing to implement these inference rules and implement these restrictions。

So it's worthwhile in homework for homework4 reading these rules and making sure you understand what's going on。

 They don't fully define the semantics of oat that you're implementing。

 but they often give you some guidelines for what should be going on。One question you may have is。

 we're kind of seeing how the local context gets。Modified， you know。

 local available declarations add things to it。 But where does the global。Environment come from。So。

The global environment。Is actually due to another judgment。That given a program。

Is going to gather up。I's going to create。A global context。

So all the program is is really just a list of declarations of global variables and global functions。

That's all the program is。嗯。And so this judgment for a program being well typed。

 a list of declarations being well type typed is， first of all， that we。

Go through all those declarations and produce the global context。

That is the global variables and the global functions that are in scope。G。

 and then we use that global context to check each declaration in turn。

 to check that each variable context of global variable declaration makes sense。

 to check that each global function definition makes sense。诶。

So this thing here that goes and gathers up all of the global declarations。

 that's this judgment right here。And you can see that what it does is starting with G0。

 it just goes through each declaration in turn gathering up the declaration。

 threading that through to get to the。The final global context。And。All this judgment does is。

Check to make sure that global variable declarations are okay， that a global variable is unique。

 doesn't really exist。That the global initialer makes sense with respect to an empty global and local environment has the appropriate type and adds that to the global declarationation。

And in a similar way for a function declaration， it just checks that the function name is not already defined。

At this stage， it ignores the block。 It ignores the function definition because all it's doing is gathering up the names that are in scope。

It adds that function definition to the global set。I will say that G0。Is。Essentially。

 the set of built in global declarations。 So these are like the built in functions that you might use to print string。

What are some of the other ones？Number to string， I think is one of them。Yeah， so that's G0。

 the sort of built in functions you might be able to use， but you can declare your own。So again。

 this is a really succinct and elegant way of specifying many， many parts of the language。😊。

And we haven't given it to you， but you could also define the actual execution of the language。嗯。

Using inference rules， like using an evaluation judgment。

Any questions about these homework 4 inference rules？Okay， in that case。What's。

Spend a little bit of time seeing how this plays out。In the sense of。Those are the inference rules。

 But the important thing is actually using those inference rules to construct trees。

 That is to be able to show， for example， that a statement or a block is， in fact。

 well typed that is's doing the correct things。So。We're going to go over this relatively quickly。

 but the idea being that we might have a program。Like this that has a number of variable declarations。

嗯。And the idea that we can take those inference rules and instantiate them。

 I think my slides might actually have an old version of the type checking rules that I haven't updated。

 so don't look too closely at this， but the intent is of course， that we take the inference rules。

 we instantiate them and appropriately we come up with the finite proof trees。

The trees get big quickly。so if we were trying to prove that this sequence of four statements is well tapd。

嗯。This might involve checking that。

![](img/5ab24c3086ef056c29825f3b3e5bf0f4_5.png)

Using a rule that requires。The sequence is okay。 and here it produces the local environment where x1 and x2 are in scope。

 then would need derivations for each。Of these to show that each of these statements are well typed。

The slide's too small for me to show that， so I'm using D1， D2， D3， D4 stand in for the derivations。

 the proof trees that are going to prove each of the appropriate premises。

Let me show you those derivations quickly。So the first one。

 D1 would be a derivation to show that y x1 equals0， that that declaration is well tapd。Right。

 so that would be like we saw using。A different judgment to reason about declarations。

 there would be checking that the expression is well typed。嗯。And so on。

 and it allow us to conclude that this variable declaration is well typed and it adds x1 into the local context。

Wed take that new local context and use that as the local context for checking the second statement V x 2 equals x1 plus x1。

 So here we see that we are。In our local environment we have x1 and scope， similar thing。

 this is a variable declaration with the initializer x1 plus x1。

 so you can see that we have a tree that is checking to make sure that X1 plus x1 is appropriately typed。

 so here's an expression judgment。Here， X1 plus X1 is a type and。

And that's breaking down into the left and the right upper end， both of which are variables。嗯。That。

 of course， introduces a new variable x2 into the environment。And so we thread that new environment。

 the new local context containing the X1 and x2 as the local environment to check the third statement。

That x1 equals x1 minus x2。Similar of the thing， this is an assignment statement。

So we're going to check that。X1 minus x2 is of type nt。 I see here's one of the places where。

My derivation isn't reflecting the latest version of the rules。

 where I should have another premise saying that x1 is of type int， the same type as the expression。

But you can imagine how you boot up these derivations， you boot up these trees。

Here is the fourth derivation showing that return x1 is well typed。

 namely that the expression we're returning x1 is of the return type int。

 which was this part of the context of the left hand side of the turnst。Right。

So this tree gets big quickly。 This was just a full line program。

 So we typically don't actually look at the trees directly。

But it's important to understand this idea that from the inference rules。

 the point of the inference rules is to be able to instantiate them。

Into forming these proof trees to be able to prove。That specific programs。

 the program we're compiling the program with type checking is， in fact well typed。

Any questions at the moment？We've touched on type safety a couple of times in last lecture。

 looking at type safety for this simple。Fal programming language。In general。

 type safety for a more powerful language。嗯。Typically takes the following form。嗯。

The thing about more general languages， more powerful languages as I talked about how simply typed lambda calculus always terminates。

But in a powerful enough programming language， you want to be able to write non terminating programs or programs that might terminate or not terminate depending on the input。

So type safety typically takes the following form。 If P is well typed， then either。

It terminates in a well defined way， or it runs forever。And by terminating in a well defined way。

 this is gonna depend on the language。 but then might be that it halts with a return value。

 maybe due to a return statement， or maybe raising an exception in an appropriate way。

 The old language doesn't have。Exceptions built into the language， but languages such as Ocal， Java。

 Python， These are a well defined part of the language and a way of the program terminating in a well defined way。

The important thing is that type safety does rule out entire classes of undefined behavior。Including。

You know， unsafe casts， that is where， say you might treat an integer as a foot or a pointer or vice versa。

 treating noncode values as if they were code。That is something that low level languages like assemblyly don't have and is a source of many security vulnerabilities is where data provided by an adversary ends up being treated as if it were code。

嗯。Breaking type abstractions of the language。 So， for example。嗯。

One of the ways of doing that is essentially。Treating something as if it were the wrong type and thus being able to treat values inappropriately。

嗯。But might also include， depending on the features of the type system。

 say things like who is able to modify a variable。In some languages the code that can modify a variable might be restricted to the code that's used to implement that module。

Right， and even though you might have。All values being treated at the appropriate type。

 part of type safety or the type abstraction might be nobody outside that module can modify that value。

In general， what is defined will depend on the language semantics。

 and you can't make it precise for a specific language。Okay。Any questions at the moment on。

The typing of vote or type safety。Okay。I want to take a bit of a segue at the moment。 So this is。

Taking a look at。呃。Think about compilation as a judgment。rather， as translating judgments。嗯。

And I'll imagine that we have a source language that has a judgment。In context C。

 expression E is well typed with type T。We're interested in compiling。A program E。

And a lot of the time， in order to compile E correctly。

 we need more than just the expression E itself。We actually need additional information。

 the context for sure， we need to know what variables are in scope as we compile E。And often。

 other information about that judgment turns out to be useful。

 like knowing what type the expression is might help us as we're ending up compiling that expression。

嗯。Also。As we're compiling E。😡，We're going to be compiling the subexpressions of E。

And in a similar way， it's going to be useful for us to know the context and the type。

Related to that sub expressionpression。So essentially when we're compiling。

What we might actually be doing is。Taking a look at the proof tree。For the world typedness of E。

So in some ways， what's going on with many compation processes is。

What we're really doing is taking a proof tree。In the source language。

So the proof tree that he is well typed。And essentially visiting that tree or maybe transforming it。

Into something else that is essentially the compilation process。And so you can think of that。

Transformation of a judgment or of a proof tree。Into a target language as being。嗯。

As being compilation。And so we can end up。Thinking about the translation of the interpretation。

 the compilation of each of these components。So the translation of C。Translating。

 if we have a context at the source level， saying this source program variable has this source type。

We might want to translate that into。Here is。At the target level。

 information about how to access a particular variable and the target level type。Of that information。

It might also be translating types， so source types are going to be represented in some way in the target level。

 so we might have a translation on types。To understand how they're translated。

What we've been seeing in our compilation that you've been doing in homework 3 is you're translating an expression。

Into a stream of instructions。Such that when that stream of instructions is executed。

 it computes the result of E and puts it into some operaand。Right。And so。

If you think about it in that way， our translation of this typing judgment。Gives us back。

The result type and the target language know is the translation of T。

It gives us back a stream of instructions。That's going to compute E。

And it's going to give us back an opera end with the result of the years available。

And the invariant of the compilation， the reason the kind of reasoning you need to do。

And your implementation is that。The stream。Compututes E puts the result in opera end。

 and the value in that opera end is of type TY where TY is the translation of T。

Kind of that invariant allows you to recursively。Use the typing inference rules， if you will。

To translate， let's say， an addition statement。By recursively translating。

 compiling the subexpressions and relying on the fact that the result of translating those sub expressionions will meet this invariant。

 you know the opera ends where the results of the subexions are available and you know that they're going to have the appropriate type。

 I64， for example。So to see that as a simple example。

 if we were trying to show that 37 plus 5 of type int。

 So if we have this judgment at the source language。Translating this judgment。Is really about。

Translating that proof tree。That we're going to end up translating the subexpressions， 37 and 5。

So translating 37， we don't need any stream of instructions， we can just use the opera end cons 37。

 the result type is A64。Similar similarly for the second opera 5。And then， we're going to。

Take those recursive calls and combine them together。Into the translation of 35 plus 7。

Here's an instruction that assigns a new UID using an ad instruction。

 using the operas from the premises， and the result is stored in temp。

And so the implementation you've been doing has kind of been doing this already。

But this is kind of making it clear and explicit。And to be honest with you。

 putting it in a form that。Is amenable to reasoning。Even to proving。That the compilation is， in fact。

 correct。 It's not something we're going to dig into in this class。

 but this is an exciting area of research and increasingly of state of the art systems。

Where you can end up proving that the compiler is producing correct code。

 essentially by reasoning about these kinds of。嗯。Transformation of judgments。

 and in the same way we're able to prove type soundness。

 reason that a type system can ensure certain properties of a program。We can reason。

 We can prove that compilation like this。Ends up being correct。

Producing target code that is equivalent in a very precise sense to the source code。嗯。We do。

 of course， need to translate the context as well。And essentially when we do that。From the source。

Context maps verbal names into。Soce types。What's useful for us in compilation is mapping those source identifiers。

To target types and also a way of accessing。That variable， like where to find it。嗯。In Oat。

 we actually had， there are two ways that we use variables， right， because variables are mutable。

 As you know， you end up using a variable both to as a value。

When it's on the right hand side of an assignment， when it appears it an expression。

But you also ended up using it as a location。When you need to assign into it。嗯。

So what that boils down to is hopefully you've all been finding， as you've been implementing it。

 and I believe this is in the hints。They're just translating all of those local variables and global variables into pointers。

 so that it's kind of easy to treat them in this way。

Both as a location to be modified and also to get their value。嗯。

And so the invariant that we're using wanting to use here is that if at the source language。

 I have a variable x of type T in my context。Then in my translation of the context。

 I want to be able to look up that variable， get back。An opera end。

And the type of the value at that opera end is going to be a pointer to a value of type T。

And what that allows us to do is to think about when we're translating。

An expression denoting a value。We can translate that to we look up that。

The variable X in the local environment。That gives us an identifier and the type and then we load through that pointer。

To give us the result。By contrast， when we're treating it as a location to be assigned into。

That same context。嗯。Can allow us to store。Into the pointer。

Store the result of the expression E or other X。Into their pointer。 that allows us to treat。

These mutable variables in a uniform way。Any questions about this， Very。

Quick hand sketch hand wave about this idea of transforming judgments。

And being able to reason about compilation as a formal process。ok。So with that。

 I want to kind of end this sidebar， this divisionversion into。Think about transforming judgments。

Let's get back to type。So one of the ways you can think about types。

 the way I introduced it initially is as an approximation of computation。

RightThe type of an expression E is type int。You can think about that as。In says the computation。

 if it terminates is going to produce an integer value。An equally valid way of thinking about types。

Is to think about them as identifying a subset of values。So when we say x has type ins。

 what we mean is。If we， if the expression X evaluates to a value。

 then that value is going to be in the set。Fed by int。

You think about sets as just being predicates on values。嗯。诶。And typically， though。

 the sets that we think about the sets of values that we think about with respect to types are very simple predicates。

 whether a value is an integer， whether it's a boolean， whether it's a function。However。

 we could actually have。Types that are more interesting predicates on values。

Instead of just saying it's an integer。We could actually have a predicate， a type that says。

It's a positive integer。An integer greater than zero。And another type that says。诶。

The set of all inages that are negative。And so。You can imagine extending a type system。

With these fine grained sets of values。So that in addition to the type int， the set of all integers。

 we might have the set of positive integers， the set of negative integers。

 the singleton set containing just the zero value。Same with Booleions。 you might have。

 in addition to the Boolean type， you might have the subsets of booleans that are true。

 the singleton set， samee with false。 Maybe we add a type that is any value at all。

 integer Boolean and anything else。So that's kind of cool。 right。

 What this means is that you could extend the type system。😊。

With these more interesting predicates on values。And then your type system is actually telling you something。

Even more interesting about the computation。Instead of just saying we may better come up with the type system that says this expression。

 instead of just evaluating to an integer， will in fact， always evaluate to a positive integer。😊。

That's pretty cool and goes beyond what we see in type systems of many current mainstream languages。

If we add these new kinds of types， these fine grain types。

 we your course need to modify the inference rules to reason about those types correctly。so。

Sometimes those modifications are going to be pretty straightforward。 So for example。

 for integer constants。Maybe we have。Three rules for the positive case， negative case and zero case。

 instead of just one case that's said integer。Same with Booleions， right。

 We'll have a rule for true that says it's of type true， a rule for false， saying it's of type false。

So what about an if expression？So what's cool here is that there's a couple of cases that are nice and straightforward to modify the typing rule。

And actually get a whole lot of precision。So if we have a if statement， if he won， then E2 LC3。

And E1 is of type true。Right， that means that E1 when it evaluates if it terminates。

Is going to return a value in the set designated by the type true。Meaning， you know。

 there's only one value in that's set， the true Boolean。

 So that means we know that if E has typed true， it's always going to evaluate to true。

So that means we know that E2 is going to be executed， so we can check to make sure E2 is well typed。

And the cool thing is we know that E3 will never be executed， so we don't even need to type check it。

Because we know it's never going to be executed。In a similar way， if E1 is of type false。

 we always know that the else branch E3 is going to be evaluated and the true branch never will be。

So that's cool， right， that's a nice， precise typing rule。That that allows us to admit more programs。

 even programs with the dead code， the branch that has never taken。Doesn't do good things。

 we're not going to reject the program because we know that code's never going to execute。But。

 of course， a lot of the programs that we're going to be writing。

That God will sometimes be true and sometimes be false。So。In that case。

Let's consider the following program effectses of type Bo。If x then 3 else negative 1。

Sometimes this expression will evaluate to three， a positive integer。

Sometimes it'll evaluate to negative one， a negative integer， depending on what the value of x is。So。

What should the result type of the whole if statement be， right， The two branch has type pause int。

 Fo branch has type Ne int。William are we allowed take unions of。

 Are we allowed to take unions of sets， That's the exact right intuition。

If we're thinking about types as being sets of values。Then the appropriate type for an expression。

 we kind of to be precise， what we want it to be is the small is the type that is the smallest possible set。

That contains all the possible values that it might evaluate to。So for， for us in our sitting。

If you're the union of pause and Neg。😡，The type that contains both paws and nig。Is int。まあ。Besides是。

Well， that's the interesting thing。 In the type system we presented。

 we don't actually have a type that's。Nonze vintages。So let's dig into this a little more。

 This is the notion of subtyping。And upper bounds。When we think about types as sets of values。

 there's this natural inclusion relation over types。So the set pauses representing of positive intes。

That's a subset of the set of all integers。And this idea of the subset relation。

On the set of values that a type represents。This gives rise to the subtype relation。

So we want to say that pause is a subtype of int。And the way to think about that is。

Pauses are subtype event， for our purposes。If。The set of values the pause represents is a subset of the values that it represents。

 which is the case。Well， generally， the subtyping relation gives rise to a subtyping hierarchy。

Okay so here are all the types we had in our language， right， we had Neg， zero， pause， ints。

 true falsepool and any。OkayThese were the only types we had in our language。

 So note that this is not every possible subset of values。We're kind of in this case。

Defining beforehand the set of the types that we're interested in。

And any given type represents a set of values。And we have this subtyping hierarchy of the types。

That is int。The set of all integers is a super set of the set of negative integers。

 and it's a super set of the singleton set 0。 and it's a superet of。The state of positive vintages。

So in general， given any two types， T1 and T2。And given this。A subtyping hierarchy。

We can calculate the least upper bound of those two types that is。Within this hierarchy。The set。

 which is an upper bound on them。That is which contains all the values of those types。

 but it's as precise as possible。 It's as low。In the hierarchy is possible。

 that is the smallest such set。So for example， the least upper bound。

 the lub of true and false is bull， that is true and false in this subtibing hierarchy。

 the least upper bound is bull。Any is also an upper bound。But it's not a least upbound。

In a similar way。The least upper bound of int and bull。Is going to be any。

The least upper bound of int and true。Is what？Any， least up amount oft and true is any。

There were the Ss。We picked some collection of types to use。Maybe for the purposes of your language。

 you wanted to add in some other types， such as。Non zero or non negative or non positive。

And they would end up adding new types， they would fit somewhere in this subtype hierarchy。

And would allow you to have maybe more precise。Lest up a bounds for certain things。Right。

But that's a design choice in the language。Okay， so if we go back to our typing rule for if。

In the case where E1 is a bull， we don't know whether it's at runtime always going to be true or always going to be false。

 Here is an appropriate typing rule for it。We type E2。And we type E3。

 and they're going to have respectively Lee types， T1 and T2。And the type of the whole。

 if expression is going to be the least upper bound。Of T 1 and T2。

So that's going to be essentially the most precise type。That our type system allows。That describes。

A value with either type T1 or type T2。It turns out that what we want in our subtyping hierarchy is。

系。A join semila for those that are familiar with it。

 And so the notation and the term knowledge that we use for least up a bound comes from that area of mathematics So we might write it with this V symbol or a square cup symbol。

 and we often call it a join operation。嗯。The subtyping hierarchy satisfies some properties， right。

 It's a partial order， meaning that we want this relation， the subtype relation to be reflexive。

Transitive。And antisymmetric。Okay。Do I need to dig into details on any of these， if you want。

 I'm very happy to sort of talk our way through。What these axioms mean， what these properties mean。

People， I know people in 150 who took 152 were very comfortable with these relations。

 Are they covered in other courses。Do you see it in CSs20？Nods。Okay。All right。

 if you have any questions about these， feel free to post on Ed and happy to discuss them further。

Okay。As I mentioned， we don't have a type for every possible subset of integers as a type。

 So for example。In the type system we had， we left out non negative types， we left and so on。嗯。

We can talk about the soundness of a subtyping relation。If。

Essentially the intuition that we have about subtyping is in fact true。

 that is if the subtyping relation does correctly approximate that underlying subset relation over values。

So more formally， we can think about。The denotation of a type。

 which we're writing with these double brackets。Around the type T as being the set of values of that type。

So for example， the den notation of0 is the single to set0。

 the de notation of pause is the set of all positive integers。And then。Our subtyping relation。

Is sound if。The following holds for all T1 and T2， if T1 is a subtype of T2。

Then the denotation of T1 is a subset of the denotation of T2。

That is the set of values that the T1 represents。Is a subset of the values that T2 represents。

So for example。Pause is a subtype of int is sound since the set of positive integers is a subset of all of the integers。

If it were around the other way， it wouldn't be sound。

 the set of all integers is not a subset of positive integers。And so w。

 and so this gives raise this intuition for the subtyping relation is really reflecting that subset relation part of the intuition for way the relation should be reflexive。

Tsit of an antisymmetric， as that's properties of the subset relation。

We can also talk about the soundness of the least upper a bound relation。

The idea that the least upper bound relation should be an over approximation of set union。That is。

Given T1 T2 and the least upper bound of T1 and T2。

What we want for soundness is if we take the set of values that T1 represents。

Union that with a set of values that T2 represents。Well。

 the love of T1 T2 should definitely be an upper bound， right， It should， in fact， be a super set。

We do also want it to be the least such， the smaller such thing in the language which I haven't written up on the slide。

But。If it isn't， then that should fall out somewhere else as an unsoundness somewhere else in the subtopping hierarchy。

Okay， so here's an example to show that enters the least upper a bound。

Of zero and pause rather than it sound。嗯。The de notation of 0 is the synchron set 0， de notation of。

 the positive integers。 So that's the set of natural numbers。With is a subset of all integers。

 which is what is the least upper bound of0 and pauses。And。

This idea of the soundness of least upper bounds。It's essentially the intuition for way typing rules like this are sound。

What they're doing is giving。An approximation of the runtime behavior。Of the expression。

 we know that if E1， E 2 else， E 3， it's going to evaluate to evaluate either in T1 or in T 2。

 depending on which branch was taken。And as a result。

The least upper bound of T1 and T2 is going to be bound approximation to what this expression can evaluate to。

Any questions at the moment about the subtyping relation？And this idea of subtyping in a language。

Yeah，die yeah， just not was I know we had the arrow of。2 poems。

Would that does the arrow go like right left or？Let me show it to you on the next slide because I do have the subtypepe relation appearing here。

 but the intuition is that it was that greater than or rather the less than symbol followed by a colon。

And the。Smamaller thing is the subset， so it's kind of intuitive in that way。So the smaller here。

 the subtype。喂。Yes， smaller here is a more precise， smaller set。So。

Luckily the intuition goes around the correct way。So if we see here。T is a subtype of S。

And the de notation of T should be a subset of the denotation of S。Okay。Okay。嗯。

One of the things that's common in type systems with subtyping。Is that。

We have a single rule in the type system that refers to the subtyping relation。

And this is known as the subsumption rule。So what this rule says is。If I can show， if I have a proof。

 that expression is of type T。And。T is a subtype of type S。Vin。E is of type S。

 so this is saying that the type S subsumes the type T。Anywhere。嗯。If I can show that E is of type T。

 I can show that it's of type S。Alternatively， you can think about this is if I have somewhere in the program that's expecting a value or an expression of type S。

It's okay for me to have an expression of type T instead。So what that means is that。All of the  type。

 all of the typing rules can simply。You know， say the type that they're expecting and the only place that the subtyping relation shows up in the typing rules is in the subsumption rule。

So that's kind of nice， right， This whole complicated subtyping hierarchy doesn't really affect our inference rules。

 except for the addition of one new inference rule。😊。

That lets us use the subtyping relation to treat expressions at the appropriate type that we need。

However， there's a downside to the simplicity of adding subtyping to your type system。And that is。

The problem that imagine you were trying to find a proof。For a particular judgment。

Now the nice property that we had previously in our tape systems up until this point。Is that。

If you had a particular syntactic form。A function definition， a function application。

 an addition expression。There was exactly one inference rule that had that as the conclusion previously。

And what that meant is when we were searching for a proof tree。

 we knew exactly which inference rule to train instantiate and to recurse into。

The problem now is that with the addition of the subsumption rule。

 there's now more than one inference rule that can match。A conclusion。So given any syntactic form。

 you could always match the subsumption rule。So this actually complicates the search for an appropriate proof tree。

It can definitely apply anywhere since the subtyping relation is reflexive。

 so if you just end up saying， hey can I instantiate the inference rule。

 yes I can and now I just need to find an appropriate an appropriate subtype oh。

 sees an appropriate subtype you might end up in an infinite loop while you're trying to search for proof tree if you're naive about it。

😊，So what actually ends up happening is。A lot of the time。

 a different approach is taken to the type system instead of simply adding a subsumption rule。

Often there is no subsumption rule， and instead the subtyping relation is carefully added into the premises of all of the other inference rules to indicate the places where subtyping is allowed。

In order to make sure that your algorithm。That's doing type checking or type inference。

 that searching for a proof tree is actually a decision procedure。

 that you're not going to get stuck in an infinite loop as you try and apply different rules。嗯。

That style of reference rules where you make sure that the subtyping judgments appear。

In the premises of your rules， that is and any syntactic form has exactly one inference rule with that syntactic form as a conclusion that's often known as an algorithmic type system since it lends itself quite cleanly to an implementation。

Do an algorithm for actually finding a proof tree。Any questions at the moment about subsumption。

 subtyping and the inference rules or anything else？Yeah。

 but's somewhat tangential but I remember in like CS50 London we talked about object oriented programming。

 there was some concept of like you can passing in inherited classes into。This is really interesting。

 Yeah， so object oriented languages。😊，Yes， that's the place where subtyping comes up。

 and the idea that if I am expecting a value of type。次。And S is a subtype of T。

 then I can use S wherever I expect to use T。It turns out that in many object oriented languages。嗯。

The notion of subclass。Is not exactly the notion of subtype。

So it turns out that an object onlyiented languages that are class based。嗯。

Subclassing is really an inheritance mechanism， a code reuse mechanism。

 how to make sure that when I define a subclass， I can make its behavior。

Inherit various things of the superclass。But。For subtle reasons， it is often not a subtype。And。

I' just say for those who have taken 152。The issue comes up essentially with the subtyping relation on functions。

 computations。Is contrapositive in the arguments。Whereas subclassing is。Sorry。

 contravariant in the argument in for functions， but in object oriented language with the subclassing you're typically covariant in the arguments and this discrepancy leads to。

Situations where subclassing is not the same as subtyping。

And so various language designs end up getting around this in a variety of ways。

 more expressive type systems can lead to subclassing being。诶。Comparible with subtyping。But yes。

You're heading in the right direction that in object oriented languages， subclassing is very。

 very similar to subtyping with a lot of the same。Benefits。That's some subtleties。Cool。

 thanks for the question。Any other questions on subsumption subtyping in general？Okay。

 one last thing I want to say about subtyping， it's really cool。It's really powerful。But。😡。

In a real programming language， it's sometimes too confining。

 You sometimes actually need to explicitly cast a value。From a supertype into a subtype。That is。

 the type system might say something like this is an integer。But what I want is， let's say。

 a positive integer。 I want a value of type pause。So。What do you think you'd need to do？

In order to safely。Downcast value。That is， in my program， somebody gave me a value of type int。

 I need a value of type pause。What do you think you'd actually end up doing to make sure this is okay that your program doesn't have any woodfined behavior？

Any know one else that we haven't heard from， thanks for having him。

 I see your hand and thank you Abe。😊，a lot of way that languages due reflection is five story on time。

そいから。Yes， that's really interesting。😊，We haven't talked about this yet。

 but some languages do actually have a representation of the type at runtime。

And so with an object oriented language， this makes a lot of sense。

 you know the runtime type of an object and so you may end up saying。

 hey is this runtime type of the object subclass of this object that I care about。So that is。

Something that the language mind up doing。In our setting， though。

 let's just think about if we think about types of sets of values。

 we actually have a simpler approach。Are you rules？Determine how you can cost。Yes。

 we can definitely add inference rules that allow us to safely downcast。But intuitively。

What would you do if somebody said if you were writing a program and somebody said， here isn't it？

I need a positive integer。 Yeah， Maxwell， if it's in the subset then you need then just change the type and if it's not。

Very assertive warrior。Right， so check to see whether the value you get。

Is actually in the set of things that you're intending。So。And and we， of course。

 need typing rules to allow this。 So that's what Murray was talking about。 the idea that， you know。

 because we're actually interested in a set of values， the value itself is around at runtime。

 So that's the thing we can check。 a more sophisticated type systems。 You're right。

 We might need a representation of the runtime type。 But Maxwell's suggestion of。Essentially。

Let's take a look at the value we have and check if it's in the subset。Right。

 so the kind of thing that we。My want to do is。嗯。Explicitly downcast。

 there's a number of ways that this might happen。Here's。

So you might actually imagine adding in a special statement that said something like。Is。Is pause。

And the result of his pause is either or you know cast a pause。

 either gives you back a value of type pause if it's a positive integer or it throws an exception。

Another option is this kind of check downcast。 So here。嗯。If Po x equals E1， then E2， LCce E3。Well。

 let's check the guard E1。Hespi of type int。If it's positive。

 then we're going to execute E2 and inside E2， that value。Is going to have the type pause。

The more precise type。Right。Otherwise， an E3。We don't have that additional information。

So essentially the idea here is that there's a dynamic check of the value and based on the result of that dynamic check。

 we can have more precise type information in some circumstances。嗯。呃。So you could imagine that you。

Could end up defining operations Now we're at a state where we could give integer division the type int。

 arrow non zero arrow int if we had to type non zero for nonze integers。

And simply Integer division having that type would mean that the programmer could only use it。

If they prove that the divvisor expression is nonze。

Maybe they can do that because it's a constant and their constant will have the appropriate type。

 but if it's an arbitrary value， then they might be forced to do some type of check downcast。

 checking at runtime that the value is nonzero。so that's kind of cool how the type system。

 a more precise type system， can end up ruling out more kinds of ill defined behavior。

And the subtyping relation is a very natural way to do that。And kind of puts the。

And requires the programmer to do dynamic checks when necessary。

 but if they statically know that a value is appropriate， they don't have to。Right。

 so that's kind of nice。 you perhaps get the benefit。

 all of the benefits of the expressiveness of being able to have。

Programs are computer anything you want， but without the runtime checks。

 in the case you can statically prove that you're okay。Okay。

That's it for subtyping in Monday's class， in addition to some other things。

 we'll be looking at how we're going to be using subtyping and homework 5。

 that is part of your part of the O type type system is going to involve a subtyping hierarchy and new。

A new kind of program construct that checks， does this kind of checked downcast。Okay。

 thanks very much， everyone。 Good luck as you keep on working on the homework assignments。

 and I will see you on Monday。😊。

![](img/5ab24c3086ef056c29825f3b3e5bf0f4_7.png)

![](img/5ab24c3086ef056c29825f3b3e5bf0f4_8.png)