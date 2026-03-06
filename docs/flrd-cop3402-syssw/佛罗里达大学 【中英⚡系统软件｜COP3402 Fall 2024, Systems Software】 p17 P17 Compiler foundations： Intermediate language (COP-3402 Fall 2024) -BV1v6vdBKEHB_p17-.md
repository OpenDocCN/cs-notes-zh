# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p17 P17 Compiler foundations： Intermediate language (COP-3402 Fall 2024) -BV1v6vdBKEHB_p17-

Welcome back to System softwareftware。Today we'll finish up parsing from last time。

 and then we'll move on to our intermediate language that we're going to use for our compiler。

 that we're going to generate code from our compiler。So last time we went over。

The internals of the compiler。We went over a little philosophy about symbols versus their meaning。

And where we left off was in。

![](img/e5ff24709fe9a48cec134073d939421a_1.png)

Talking about grammars and parsse trees。

![](img/e5ff24709fe9a48cec134073d939421a_3.png)

So let me first ask about the sort of start this with talking about the homework。

So I know I didn't cover completely formal grammars and how to write them。

 sort of hoping you would do this sort of by example。

Who has an attempt they'd like to share that they did not Google。Some people's hands。Okay。

 I think you were first。No， no， white shirt， white shirt， behind you behind you。还有真。Okay。So， let's。

Let's take a look at the attempt。All right， take it away。呃，EL。N， and E。不玩。And。Okay。

 so that's all the numbers， all the digits。でい。Okay。That seems pretty close， right？Any other takers？

She like how。Yeah， it is， it is similar to that。So if the infi version is。This。Or maybe this。

This was our in fixed version that we showed in class。

This is like a schema that tells you that expressions， you have an expression on the left side。

 you have an operator and an expression on the right side， so what's the post fixed version of that。

EE op， yeah， that's really all it is actually， that's like yeah。Yeah， good ahead。O。ロスマの。ま民しな。For农。嗯呃。

まいでありま。さ。No operator no。こで说のの。So the issue with this is you also support inFX here。大た。Okay。

So this is the answer。You just say just like Infix is saying。

The operator is in between the two expressions and the expressions can either be another expression or a number。

So post fix is just。You have two expressions followed by an operator。

And I think most people had done inf and post effects， yeah。

All like these terminals like like E equals okay。えと？最近はあ。还在一。最高はそ。マ年？Master is。はいどう。Okay。

 we'll over the， let's go over how this works， so this is infi， right。

 this is what you you know as inF。And you can have nested expressions in this notation。

 so I parentheses to make clear where the nesting happens。So this is one E， this is another E。

RightAnd within those within that left hand expression。There are。There is a nested expression。

Does this make sense， this's clear？And then this symbol is the operator。

Has anyone ever programmed a Lsp before？okay， oh ws okay。

 so this probably looks a little bit like Lisp kind of this is actually a representation of a tree this。

😊，This syntax here。You can think of。Nesting。The exact same way that I nested parentheses is kind of a representation of a graph。

So this eight here， let me get the。Expression back so this8 here is its own。Is its own expression？

Let's skip the end part。Each of these are their own expressions。

And to reflect the fact that eight and three are the two operas for this plus。

We can use a tree to group them together， so this parenthetical grouping。

Is the same thing as this tree grouping。Does makes sense question not yeah。Well。

 the tree so a tree is one。Expression in the language。

 but you can think of the grammar as schema that tells you what all trees look like。

 So this is one tree for 8 plus 3 plus2， but the grammar captures what the structure is for any expression。

 So if I have another expression like，Nine times three， it's going to have a different tree。

But all those trees are captured by this grammar。still like you。Yeah， because E can either be。

An operation， or it can be a number。And because E can be nested inside of itself。

 or another E can be nested inside of an E。You can capture that relationship for a particular string using this tree to capture it。

To have the recurt， the self referential stuff。It is confusing。

So think of it like recursion in programming。So it's kind of confusing to define factorial in terms of itself。

 right？But one way to think of it is that every time factorial is called。

 it's called with a different parameter。And so you can think of that as a different function。

So instead of thinking it thinking of。Factorial is having one definition。

 You can think of factorial as having。Lots of。Versions of the function like factorial 10。Factorial9。

 et cetera。And so that recursive function is kind of like a template for defining。

 generating new functions。That have out of the parameters and so this grammar works kind of the same way where。

This is like a template for telling you how you can instantiate one。Instance of E。

So one instance of E is8 plus3， another instance of e is just8。

 another instance of e is 8 plus3 plus2。And this recursive relationship tells you how you can arbitrarily nest and create an infinite set of these possible strengths。

I don't know， does that help at all sort of， if you think of it like recursion in programming。

 it's really the same idea。O。And so for the sum of whatever this expression is。

 which which represents8 plus3， can be represented with another expression for that entire expression plus2。

Okay， so don't worry too much about。Actually， being able to write grammars can take。

 if you' really are interested in can take mygraduate compilers class。

 we'll learn about grammars and how to actually automatically parse what's that。

You can check the schedule， I think it' Monday， Wednesday， next semester。But let me okay。 So what I。

 what I want to finish up in parsing is how you can， once you have this tree。

 how you can interpret or compile this language， either interpret to get the value or compile it to another language like like assembly。



![](img/e5ff24709fe9a48cec134073d939421a_5.png)

![](img/e5ff24709fe9a48cec134073d939421a_6.png)

All right， so if you look at this， let me clear out the rest of the stuff。

So to provide some more concrete definitions of this grammar。As I mentioned last time。

 the terminals are the words of the language， those are the symbols that are actually expressed。

Those are what's spoken， those are what's in the source file。

 that's what you see or hear in the language， so what are the terminals？And this expression language。

その break。Yeah， well， the zero， the one， the two， three， four， the plus， the minus。

 the times and the slash。You can think of the word numbers。

 so whenever somebody tells you a number they say like， well， I'm 10 years old， they don't say， I'm。

 hey I'm about to tell you a number now， 10 years old， right。

 you just know that that symbol 10 represents a number because of its actual shape。

 the phonemes that it's comprised of and also of how it's used in a sentence。So 10 years old。

 you know from the grammar， the context of the grammar， that it's a number。And so nobody says， hey。

 I'm telling you a number。That's what non terminalmins do。

 nontermins are like an explicit representation， another symbol that you never really have to say when you speak。

 but they're an explicit symbol that we can use to record the type of this word or the construct that this word is used in。

So it's a little bit of a trick question to say what are the terminals。

 and if you say the terminals are numbers， well you're using a meta word for what those numbers are。

 the numbers are actually0，1，2，3，4 or the ASCI symbols for0 through nine。

Those are the actual concrete symbols and N here or numb。Is a meta word。Is metal language to say。

 here is the set of terminals in my language。And by the same token， we can use these meta words。

 these non terminals to describe other syntactic constructs like a sentence or a verb phrase here we're using it to describe。

A nested mathematical operation， a nested arithmetic operation。Does that kind of make sense？So this。

 if you look at this tree here。At the bottom， this is what you actually see or here。

 this is what the machine sees in your source code， all of this is unspoken。

But what a formal grammar does is it makes this unspoken stuff spoken， it makes it explicit。

Because the theory is， is that there is this kind of hidden grammar here。

 there is this hidden structure to this language that isn't uttered。

 that it's not said in the source code， it's not said when we talk。But philosophically。

 we assume it's there。And we can describe it explicitly in the same way we explicitly say utterance is in language。

 we can describe it explicitly with a formal grammar。

Does that kind of make sense like philosophically？It's a meta language。

 it's a language describing language。Questions that questions on that part。So in the formal grammar。

 the non terminals are symbols， explicit symbols to describe the syntactic contract to describe these unspoken things。

In the language， these unspoken structures。And then productions。

 these are the rules that tell you how the non terminals form the structure of the language。

 they tell you what these non terminals mean。Or at least how they're structured。

 So this rule here tells you that an E symbol， an expression non terminal symbol。Can be。

Instantiiateated by taking any other two expressions and putting an operator。

Non terminalal in between。So without this knowledge of this grammar。

There's no real way to concrete or there's。Without any concept of this grammar。

 it's difficult to say precisely what this expressions mean。

 you might be able to do it statistically by looking at past instances of this expression。

 and you might get that right。But that sort of begs the question of how did the people who got this right answer get it in the first place。

 but the kind of philosophy here is that without this formal grammar somewhere。

There's no sensible way， no principled way to interpret the meaning of this expression。

So these rules tell you。What all the possible expressions in this language look like。

All you have to do is follow these rules and say， all right。

 well I have an expression and I want to make a valid expression in the language then I follow this rule。

 I say， all right， I can either pick this E or this E， if I pick this E here。

I then have to can then transform， expand it into an N。

And in order to continue discovering some expression ofist language， I can look at the end。

Nonteral and pick one of its expansions， one of its rules for telling you how you expand this non terminalal into terminals and you do that over and and over until you get all terminals in your language so for instance here we have an E。

 we can pick some other E here， we can pick another E here for the left side and eventually expand that into a terminal8。

and do the same thing for this entire tree， and we'll get one of the instances of this grammar。

 one of the elements of this language starting from our starting symbol。Yeah， yeah， exactly。

 it's a finite description of all the infinite set of all possible expressions。

So that's kind of the cool trick of it is that this technically defines an infinite set of possible expressions。

And it comprehensively describes all possible expressions。At least in this language。

But we can describe it finitely。Using nonturns using the grammar to define it。I questions on this。

 at least kind of philosophically the distinction between。A tree for a particular。

String in the language and the actual the grammar that describes all the strings in the language。

So it's a lot like regular expressions if you learned。

 I think not everyone learned regular expressions yet， but it's related to regular expressions。

 regular expressions do something similar where they define an potentially infinite set of strengths with a finite representation。

Okay， so let's see how we can use that， so this allows us to find the kind of hidden structure of our language。

And once we know the syntactic constructs that are being used to express this expression。



![](img/e5ff24709fe9a48cec134073d939421a_8.png)

We can use this tree in order to define。An interpretation to find the meaning of this language。

So I showed this briefly last time， but let's。Intuitively interpret。😡，The meaning of this tree。

 so we're going to assume that this is an arimetic expression and we're going to use the kind of conventional meaning of arithmetic expressions to try to deduce what the resulting value of this expression is。

All right。What's the value of the ASCI8 symbol？In our kind of computer language。Well。

 that's the number for eight。But in our programming language。

 and if we want to compile it or interpret it， we want this eight to be the actual mathematical number eight。

So that could be the machine representation eight。That could be some abstract mathematical object8。

ButThe value of this eight symbol。The value of this8 symbol is the math number eight。

Deote this in red to make it clear。The distinction between。Mass number eight。



![](img/e5ff24709fe9a48cec134073d939421a_10.png)

And ASCI symbol8。And let's do this for all of our。

![](img/e5ff24709fe9a48cec134073d939421a_12.png)

All of our symbols。Okay， and assuming this plus has the mathematical meaning of addition。

How can we derive the value of this？Expression E。Yeah。

 so the meaning of this is take the left hand side whatever that is， take the right hand side。

 whatever that is。And perform mathematical addition to get its value。

 So what's the value of this E here？It's just eight， so we can make a rule that says。

Whenever we have an expression that expands to a number， we just copy it。Value。

To get the value of this note。And same thing for this expression y。And same for this expression E。

So now that we know the value of the left and right child。We can。

Interpret the meaning of this plus symbol， this ASI+ symbol as mathematical addition。

And so what value does that give for this expression？外表。So we apply。

The mathematical operation of addition to the left and right child。

And so now we have the same kind of expression here， so this expression。

This rule says you have an E followed by an operator followed by an E。

 we have the same kind of node here， we have a node。

 an E expression that has an E followed by an operator followed by an E。

 so how do we compute the value of this and our rule set that we're kind of making up here？Well。

 here we so what was the rule we used for E here？😡。

The rule was whatever the value of the left hand side is and the right hand side use the mathematical addition operation to find it。

 so let's apply that rule here， what's the left hand side value。11， so we already computed it。

 we don't have to walk the tree， we just have its value by inspecting the child。

 and we have the value of the right hand tree as well。So we can just apply。

 use the exact same rule and apply。Add to the left and right child to interpret the meaning of this expression E yeah。

とつの。So it's effectively post order because you're。You only evaluate the root once you evaluated the left and right child。

 so in this case you can use a post order traversal to do this for all that's not necessarily true for all language interpretation。

 but for arithtic expression interpretation， you can think of it as a post order traversal because you need the children in order to get the value。

But it' going you can do this in some tree traersal。All right。

 with me on the interpretation of this tree。Questions about how we interpret this tree。

W's seen this before， interpreting the ortho question， so not many。Okay。

 so ass long as you get the basic idea that there there's really only two rules you need for this。

 if you have E that just points to an ASI symbol， well just get the mathematical value of that ASI symbol。

 the integer value of that ASI symbol， if you have an E that has E followed by opt followed by E。

 well just take the value of the two children， the E's children and perform，The addition。

 the mathematical edition operation， whenever you see that ASCI addition operator yeah。

Con four cases where。銀ポティの。で大会は？对。So and C， you've probably seen compiler error， right？

Or syntax error， you forgot a semicolon。 So in the programming language world。

If we can't prove that that program can be analyzed with the grammar。

 we say it's not a Valacy program。And the compiler does not even bother trying to compile it。

 it just says you did not give me a valid program and I know that because it does not match the syntax of the language。

That makes sense。Okay， so we can we can。

![](img/e5ff24709fe9a48cec134073d939421a_14.png)

We can formalize these rules or we can write these rules down。😡。

Using what you might call semantic actions or little snippets of computation that define how you compute the value。

Of this construct or this node in the tree， whenever you match this。Syntax。

So let's start with just the numbers。So for my interpreter。嗯。This version of it， whenever I saw。

Whenever I matched， the end non terminal。And it matches based on the ASCI symbol，0，1，2，3 for n。

I stored its value to be just the ASI value zero。Not very interesting。

 one I did a little differently in when I did the tree。

 but you can think of the value of just being the ASCI simple value。And the rule for whenever I saw。

 whenever you see。An expression that just consists of a number by itself。So like。This case。

The rule is。Convert that ASI value into a machine integer。

 so assuming I have some function ASI to end， we talked about it last time。

With me so far on these rules。So pretty straightforward， right， it's just rules that tell you。

That whenever you match this construct in your tree。

Here is the computation you do in order to figure out the value of that node。

 and so I just have a little syntax here to say。Here's the value， here's how you assign the value。

 you just take the non terminal name dot value， and here's how I assign the value。

 here's the rule for assigning a value to that node。And then went here。になた。あい。Ocursive and。我们现在。

I mean don't have to， there are regular languages like regular expression languages。

 and this is like formal language theory， so in regular expressions they're not nested。

 nestings not possible， so you wouldn't have yeah， you could have a language that doesn't have this nesting behavior。

Yeah。反应。By your。これと絶対の。不要力就是。都 you make the。I would just expand the syntax of the language。我 you要得。

No， I would just make a new grammar rule that says， hey， here's how you define。

Multiple digit numbers。So I mean， you could， I mean， you could use。呃。What。

 it would be called parsing context to turn this into a context。Driven or contact sensitive grammar。

 but there are already programming languages already have。

Support for multi digigit numbers and then you can just define that syntactically as well。

 you can do that with regular expression。As well， yeah。So no， this is single digit numbers。

 if you wanted to do multi digigit numbers as Martin was asking。

 you can define a grammar that allows for multiple digit numbers。All right。

 other questions on this part here。So we just get the value by converting the ASI symbol to an integer。

 and so this kind of defines the meaning。Of this grammar construct。

 this defines the meaning in terms of how you compute the value of the result。

So then for our other operators。We can compute the value exactly as we said in our rule。

 we take whatever the value of the left child is， whatever the value of the right child is。

 and we use numbers to kind of disambiguate which E we're talking about。And then we just perform。

 assuming we have a function in our interpreter called add。

We just perform the mathematical edition in order to compute the value of。This。

Expression once we match it in our input。Questions on that， does that kind of make sense？

This probably seems a little trivial， right， like almost tautological that like， well。

 why do you need to do this？For arithtic expressions， yeah。

 because our programming languages already support arithmetic expression， so we're kind of。

Just translating representations。But the key idea here is that you can formally explicitly define the syntax of a language。

 and then you can formally explicitly define for all programs what the meaning or behavior of that program is using a formal grammar。

 formal grammar with these semantic computations。So the difference is it's sort of in your head implicit。

 and you hack together a program that you think might be right versus you have an explicit description。

Of both the syntax and the meaning of this language in a way that you can actually write a computer program。

That will process for you。Yeah， it your。So so this is just a little notation to distinguish between the two E's we have here。

 so this could be like E Subscript1 or something that's often how it's done。

 so this is sort of aspects of the meta language that I'm not going to like get too far into。

But yeah， so this is just saying the first E， the value of the first E in the construct。

Questions on this。This kind of makes sense a little kind of makes sense。

So we can explicitly and formally and mechanically define。The syntax and meaning of a language。

In a formulaic mechanical way， so you don't have to hack together some random Python program to try to interpret strings and try to figure out what they do。

 you can do this in a formal mechanical way。Okay， so let's look at。Compiling this program。

So because everyone has done infi to post fix。Let me show you how you can use this same scheme。

To define。The infi to postfi problem basically as a compilation problem。

 so in fixed to postfi is basically a kind of compiler。My machine froze。何すよで。Okay。

 so you can think of the InFxed to Postfi program as a kind of compiler and we can actually frame it as a compiler using our same formal grammar annotated with the semantic computations。

 you can use the same technique to frame it， but let's go over first。What this。Compilr looks like。

 so let's take。Let's take the same program。And instead， I guess I'll do it。Blue。

 let's do translation rules。For in fixed， to post fix。So， I think。

In fixed PostF we don't actually need to know that we don't need to do the mathematical operations。

 we're just generating strings， so for eight， let's just say blue here is just the ASCI string version of this。

And we'll have the same pass through rules。For E。Okay， so what kind of rule can we apply？

If we have an E， if we have a grammar construct like this that says E op E， that's our in fixed rule。

What computation can we do or how can we generate code from the information we have on this node that will convert this expression？

Two postback。对。逃げいんです。Good， yeah， so we can define as a rule from whenever we see E op E。

We take whatever left。AsCI code is， whatever the right or string is。And we just say。

 take the left string。Take the right string。And then print whatever the operator is。

And so let's do that same process for the parent， so on the parent， we have a left。

Side child that already has the value， which is the Str 83 plus。And the right child is two。

And so let's apply the same rule， what do we get when we apply the same rule？Yeah， eight， three plus。

2。And then whatever the operator here is， plus。我了。We've just。张恩。

Weve just defined the rules for an in fixed to post fixed converter as a compiler that operates over。

A syntax tree， according to our grammar。Questions on that， does that sense？



![](img/e5ff24709fe9a48cec134073d939421a_16.png)

Okay。So here's how you might define these rules。Using our semantic actions that we annotate a grammar with。

 so here's the same grammar。And we have the same semantic actions for numbers。

 we just annotate the tree with the ASI value。Here， instead of converting to from ASI to int。

 we just pass through that ASI value。And then in order to compute the output。

 the value of our expression， we just do string concatetnation。

 we can cat whatever the string value of the first expression is。

 whatever the string value of the second expression is， and the operator。

 exactly what your fellow student said。So what's clear。

 this description of infi to posttics or that stack based algorithm。

 who likes the stack based algorithm？Who likes the formal grammar？It's about 5050 or really 10，10。

 80， 80 with not answering。So I just want to make clear to you that this kind of。

Formal grammar description plus these semantic rules that you could just have a little computation that defines the meaning or how you compute the value of a tree that has this pattern。

You can define interpreters can define。Translators。And when you did that in fixed the postfi program。

 you were really doing a compiler， you were really translating one programming language to another。

And we're going to use this same concept in order to create our compiler。

We're going to define a formal grammar for the language。

 and then we're going to define little rules on each grammar construct that says how we generate assembly code。

For that construct。Questions on that notion。And it's going to work。

Exactly the same way as this just in Python and with our antler parsel generator。

 but it's going to be the same idea you'll have。A function that gets called every time the parser matches a grammar construct in the language。

 and you'll define a function that will just spit out assembly code that has access to the values of the components of the construct。

Well， so how does this compiler know what an operation does？Or how does this？How does this？

Machine know what the meaning is。Doesn' it know the meeting？So the。Well。

 it depends on your sort of philosophy of mind。In some sense， this machine doesn't have to know。

 it's just following rules。And it's the rules themselves that define the meaning of the language。

So you as the compiler writer are crafting this machine to kind of behave as if it knows。

 depending on your philosophy of mind， behave as if it knows the meaning。

 but really it's just following a set of rules。It doesn't， it doesn't know how acting works。So this。

This doesn't know how adding works， This is just defining a computation to run whenever you see the symbol for a。

So remember， this symbol is matching ASCII addition symbol， the ASI+ symbol。

There's no meaning intrinsic in that symbol in the machine， because it's just an ASI code。

Its meaning it's completely determined by the machines and by us that interpret the meaning of that symbol。

 and so the compiler is the same way， and it's us as the compiler writers that write code。

That depending on what you think of。how the mind works。

 that code is either doesn't know anything about the meaning of it。

 and it's just following rules to make it look like it has the meaning。

 or you might think of it as the compiler is imbued with the meaning。

 the definition of the compiler is the meaning。Of plus。Does that kind of make sense。

 is this two meta？A little bit makes sense， so it really goes back to the distinction between symbols and meaning。

So if you can wrap your head around this map territory problem。That。The map is not the territory。

The symbols that we use to represent something are not the thing itself， so the map。



![](img/e5ff24709fe9a48cec134073d939421a_18.png)

![](img/e5ff24709fe9a48cec134073d939421a_19.png)

Is not you're not going to see people who are walking on the earth on the map。

You're not going to be able to rip the map and destroy the world。

 so the plus symbol is just a symbol， devoid of meaning on its own。

That's the job of you to write code that will。Make the program behave as if it knows the meaning。Oh。

Yes。Yeah。Yeah， if you want to compile Pcr， you have to write a compiler。

That processes Cca because remember we talk about the bootstrapivping problem。

 if you have no compiler for C and you write a C program。

 there is no machine that won't be able to compile that for you。

If you write C compiler in C and you have no C compiler。

There is nothing mechanical that will turn that into assembly for you until you write that program。

So this is the very mind bendy kind of self referential trickiness of compiler writing。

And it really comes down to this distinction between symbols and what they represent。Yeah。

 there's a lot of sort of philosophical implications to how this is kind of like the theory of knowledge。

Is it only symbols in the world or do they point to things in the real world。

 there are various philosophical views on this， but in the machine world。

 we can at least make a computer look like it can interpret the meaning of symbols using these computational techniques。

Yeah。Effectively， yeah， effectively the compiler defines the symbols。 Now。

 some programming language theorists will think that， well。

 the programming language is defined on its own， and then the machine is an instant。

But kind of concretely speaking。If you don't have a program that interprets the meaning of this。

 then at least the machine does not have has no meaning to the machine。

That's for sure because if you just like give ASI code to the CPU， for instance。

 the CPU is not going to interpret that as a plus symbol。

So the compiler gives meaning to these symbols by translating to another language or interpreting their resulting value。

And so in some sense， yes， you can think of that a compiler interpreter as an expression of the meaning of the language。

Because without it， well。There's nothing interpreting the meaning of that。

 and so in another sense you can think of our minds as ascribing meaning to symbols by interpreting what they mean。

And so that's what I was trying to illustrate with this using。

A different language that I think most people here， no one here actually knows。

 but there are some humans that will interpret this in the same way。

As this that I think everyone here can interpret。So yeah。

 you could sort of say there's some paleology here that these symbols are somehow intrinsically meaningful by saying。

 okay， well there's one stroke here and two strokes here。

But that's a little harder to do for the other symbols。 You could say that， but the more kind of。

Engineering viewing guess is that that symbols are independent of their meaning it's a different kind of。

Epiisttemology， I guess， that symbols are divorced from their meaning and we can use that philosophy to create programs。

That will。Kind of magically or artificially intelligently in the classic sense。

 interpret the meaning of symbols in a way that humans sort of do。All right， questions on this。

 questions on this。So wrapping your head around that kind of self referential meta notion and the difference between symbols and their meaning will help you。

 I think write to the pilot。楽しみでけ。Everyone would。Yeah， I think it's convention。

 you mean like why do some language like languages seem to have similar well。

 if they're compiling to assembly， then machine it's always machine code。

 and so you're always at the performance sort of you're always subject to the performance of that machine。

 and so it's up to you the compiler writer to try to have different version。

 like have output assembly output that will have better worse performance for the same program。

I don't if that answered your question， but。That's an optimization question yeah。

 to say how does a compile program， why would the same compiled program apparently or a program that computes the same thing in two different languages。

 why would their assembled program have different performance right that's like the question。

It's working out。Well， yeah， I mean， the instructions set itself are the atoms that compiler writers have available to them。

So you can't do better than that， I mean there's like micro code to like modify the instruction set。

 but if you give an instruction set and an instantiation to that in the machine。

You probably read it doesn't really have much else to do besides that， I mean。

 there may be like cash behavior or other。Agreggate behaviors of the machine that the compiler ready can take advantage of。

 like the allcaching is a big one to make sure that you're not like。

Kicking stuff out of cash with your order of operations， there's other memory behavior you can do。

 you can take advantage of the pipeline， but at the end of the day。

 you're sort of subject to the performance limitations of that machine as the compiler writer。Yeah。

Which ones oh， declare？In this one。So here I'm not interpreting， I'm not running。Addition。

 I'm just outputting， so yeah， this is one other distinction between interpreters and compilers。

 the interpreter， the resulting value。Is a number。That could be an abstract mathematical number。

 that could be a machine number。In the compiler world， the output is really just a string。

So you're just what we're going to output as literally assembly code and an assembly file is just a string。

iss just a more ASII text so we're not doing any evaluation。

 we're not trying to find the value that this program computes。

 we're just translating it to a different program that also computes。

Ideally computes the same values that the input program does。So remember you have three programs。

 there's the input program， the output program， and the compiler program。

The compiler is not trying to figure out the answer or the output of the input program。

 all it's doing is translating it to a different program， a program in a different language。

That is supposed to do the same thing does that kind of make sense that answer your question？Oh yeah。

 so this is not assembly， this is infix to postfi。This is in fixed postfi。

 so assuming you have an interpreter for the post fixed language。

 but this is not generating assembly。This is generating postd notation。Yeah。Yeah。

 and that's what a compiler expects， right， so what's the interpreter for the assembly code？

The processor right the machine In I guess it's really the assemler which produces machine code and then a machine code is interpreted by the processor。

 but yeah， conceivably if you have a compiler， your goal is to translate it into a different language that already has an interpreter or a compiler for it already。

 so for instance， the first C++ compiler from what I understand didn't generate machine code it generated C code。

And then there was already existent C code compilers。

 and so those were used to generate the machine code。But yeah。

 I don't know if does that answer your question？Okay。

 let's take a look at our intermediate language that we're going to use for our。Compilr。

 so we're not going to have to compiler a full sea like language。

 We're going to start from the intermediate language。 It's going to be a simple。

A much more straightforward language to translate to assembly than something like C so okay。

 so here's a C program。Assume I've got a function that can read an integer in and assume a function that I can write print an integer with。

 so here's an example C program that just reads in an integer， prints it out。

 then returns zero quick questions on it。Yeah that will be used， that'll be used behind this， yeah。

 you could， you could， but let's sum up this program。Questions on this program。Straightfor see。

Here is what an equivalent program looks like in our IR language。

So you're not going to have to write the translation from C to this， I just want to show you。

A C version so hopefully you understand the meaning of this language。

But this is what our IR language， our intermediate representation language is going to look like。

The first line of every IR declares the name of the function。

It declares which local variables you have， so this is a little different from C。It includes。

 declare all the local variables and all the parameters。

 you declare which of those local variables are parameters。And at the very end， you always return。

So this function and return are the mandatory parts of IR。

And then in the so called body of our function， it's not really body， it it's a sequence of lines。

Here is the sequence of IR instructions that will do the same thing that that C program did。

So here is what a function call looks like。You always capture the return value of a function call。

It's X and then we have this kind of special assignment。Symbol to distinguish it from C， I guess。

Use the call keyword and the name of the function。Oh actually forgot them times two in this experiment。

 but if you want to do some operation， you can do a single operation at a time just like an assembly。

 there's no nested expressions in this language， so this is an example of computing the value of a variable times2 and saving its result in x。

😊，And here's another example of calling a function。So questions on this。

 does this anything that doesn't look clear about， I know I haven't gone through the whole language。

 but anything that doesn't look clear yeah。Yeah， it actually going to be kind of this language。

To assembly。InRight。You can write this as a program and your compiler will turn it into assembly and run it。

I've also given you an interpreter for this language so you can check the。

Output against your compiled version。I'm actually， actually going to show that to you a little today。

All right。It's a much more simplified version of C， but it's compatible with C。

 the compiled version but compatible with C， so each file is one compilation unit。

 one compilation unit defines one function， so one function， one file。This is the like minimum。

Program and simplecy that you can have function with the name of the function and a return or a return takes an integer or a variable name in this case there's no variable so it has to be an integer so that's the minimum program。

Most programs that have parameters will look like this， you have the name of the function。

 local variables。Prameterters are always a subset of local variables。

 I promise you this will make assembly generation easier to declare the local variables and the parameters separately。

 and then you have all your instructions here。So let me go over quickly what the kind of instructions you have available to you。

 so you have assignment， and assignment is always a variable on the left hand side。

 followed by the assignment symbol， followed by either an integer literal。

 an ASCI symbol for an integer literal， or a variable name。

And variable names don't have be a single character， they're unbounded， yeah。Oh。

 we'll get to pointers， you'll have to do pointers too， thank you for asking。

If they was already going to do pointers， it's not because he asked were doing pointers。It's okay。

 so that's assignment， so this assignment is just copying the value from one。

Either integer literal to a memory location， basically。

Does anyone know what assembly instructions might correspond to assignment？Yeah。Move。

 move registers and maybe what about from a constant？

Move immediate move immediate if you remember this Okay。

 so there's also arithmetic arithmetic operations， so there's only a single operation per statement here there's no nested or large expressions。

呃。And you have one operator here， which is just plus minus or plus minus asterisk and slash。

And the operas are either a number or a variable。So no nested expressions。

 so that's their arithmetic expressions， function calls look like this。

Function calls are also assignment statements。You put the name of the variable that you want to store。

 so even if there's no return value， you have to assign something to it and in C actually avoid functions are kind of a new thing。

 but classic C always had a return value defaulting to end。So same in this language。

 all function calls will try to capture a return value you have to。Assign that to something。

 even if you never use it。And so you use the keyword call， so call is a keyword。

The name of the function， which corresponds to some other。IR file。

 or it actually can correspond to a C file， we can actually interoperate between C and our IR here。

 and then a list of variable names or numbers， so it can be more than one can be any zero can be zero or more than one or more than one。

Question so far on the syntax of this language yeah。Call X。Yeah， that's fine。Yeah， absolutely， yeah。

 this will change the value， yeah， just like can see。I can see if I say x equalsx， yeah。

 I'm going to redefine x。生面ency谁面 say。Oh， print has no meaning in this language。

 printnt is a function， it's the name of a function that has to be defined print print and has no。

 yeah， these are just names of functions that are are soon to be defined just like can see。

 So if you call the function， you know Paul's class parentheses X。

 you have to define that function somewhere， it's the same same thing yeah。あであ。Spaces， yeah， yeah。

 they're space separated， yes， sorry I didn't make that clear， they're space separated。Okay。

 and so this is where it looks more like assembly， we don't have structured code。

 we've got branching。So there are unconditional branches that I put unconditional I and put it here。

 so there arere unconditional branches， unconditional branches。This is what a。

Conditional branch looks like， actually I thought it was。Just if， not if， go to。嗯。

I think it's supposed to be just if if。The if keyword。Followed by。嗯。

I have to check the syntax to make sure I'm getting this right。So， a。If go to is just the if keyword。

And then yeah， so you have a single operator here， which is either a number or a variable。

 a single operator， which is one of these。Relational operators， another number of variable。

 the keyword go to， and then a label name。And so you can also do unconditional branches。

 which are just go to the label name。And you can make labels with just label name， colon。

So just like assembly， does this any questions on this？

hopefullyfully is this familiar from doing assembly code， yeah。Just if， it's just if。

 it's just stiff yeah， so the parsing will be handled for you。

 you won't have to actually parse correctly， but you will have to write this code so so sorry about the mix up on that。

All right， so here's what pointers look like， there are three types of statements for pointers。

 they're all various forms of memory， copy or move operations， so they reflect the similar C syntax。

 so in C what does this do？Gets the address， so this takes the address of a variable and stores it in some other variable。

For this， not in C。No， not in sea。Nope。1さ。Well， T1 should be declared as a pointer。

But when you assign it， you don't use the star， that's in the declaration。

So this language is also untyped。And in C， you could actually assign a reference to an integer if you wanted。

 a compiler if it has strict tracking on it might yell at you， but you can do it。

 you can go take the address and store it as an integer and print it out as an integer if you like and see you can kind of subvert the type system。

Yes， they can change the value。If you' modify， yeah， yeah。

 you can do point arithmetic and see yeah you can mess with the yeah you can mess with addresses and see。

 but yeah， so this is what the structure looks like。

 you just have the name of variable on left hand side to store it in， there's no types here。

 there's no type checking just like in many IRs。Okay， so what does star T1 do and see？

D referenceence right good， so this is the D reference。

 it'll take whatever the value of the memory it'll follow the memory location in T1 and then get the value of that number in the address All right and what about if I assigned to star。

A second。先たい。Right， it's dereencing T1。 so if T1 is an address， so at the end of this。

 what's the value of x at the end of this？11， good。 Yeah。

 So we' we're taking the address of X storing it at T 1。

 and then we're dereencing T1 to store the value 11， so。T1 is pointing to。X x is value Okay。

 so those are all of the operations in line， let me give one example of which has the correct if taken here。

 let me give an example of a program of computing an exponent。So remember。

 all programs start with a function if you have local variables and parameters。

Define all the local variables that you're going to use ahead of time， including the parameters。

And then define which subset of those local variables are parameters。

 so this is kind of the header of your program， and then at the end there should always be a return。

All right， here's the body of our program。We've got and it looks very much like an assembly version of this。

 so we start with assigning result to one。We've got a label here because we're going to jump back to it。

And so whenever exponent is less than or equal to zero。We stop， we go to the end。

So if you input a program that has an exponent of zero， what's the value of any number to zero。

 it's one right so this will correctly compute that if it's not zero。

 then we multiply result by base， so it's just repeated multiplication right for exponent and then we subtract one from the exponent。

And we unconditionally branch to top and check again over and over and over。

Questions on the algorithm for exponent。Hopefully you've seen something like this。

Questions on the syntax of simple IR。Yeah。咁。Yes， there are thank you。 Yes。

 there are supposed to be columns before the equal sign。 I have a real version of this。😊。

That I actually ran。嗯。This is what I'm supposed to。Sorry about that。

ThisThis is what its supposed to look like， yes， there are colons before the equal sign。Okay。

 so you know， I'm not a good mechanical parser， I don't expect you to be either。

 but your homework for tonight is to。Take a stab at writing a program in S IR that computes factorial。

You can do it iteratively， you can do it recursively， yeah。You can just make， yeah。

 you can make a main function， just you can make a factorial function。 you don't have to call it。

 You can just make one function， so try your hand at。Writing a factorial function in this language。

 and then next time we'll actually start looking at how to compile this language。All right。

 thanks everyone。

![](img/e5ff24709fe9a48cec134073d939421a_21.png)