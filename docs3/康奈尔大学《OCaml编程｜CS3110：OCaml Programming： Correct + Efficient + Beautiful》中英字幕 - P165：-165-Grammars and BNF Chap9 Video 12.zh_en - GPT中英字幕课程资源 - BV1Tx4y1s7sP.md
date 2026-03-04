# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P165：-165-Grammars and BNF Chap9 Video 12.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We were able to parse expressions that had white space and parentheses and precedentnce of operators。

And all of those somehow ended up getting converted into a tree that represented how those individual tokens related to one another。

So the parentheses became irrelevant in the tree they were represented by the shape of the tree。

 and the operator precedence was represented by how the tree got structured。

 which subtrees became part of other trees。We can write down all of this with what's called a grammar for the language。

 This is a kind of mathematical notation。 An expression can be one of three things。

 So an expression E here is a meta variable I'm saying meta variableable to distinguish it potentially from variables in the source of the programming language so if we were writing a grammar here for Ocal。

 as opposed to our simple calculator language， we would need to have Ocal variables as part of it。

A meta variable here is instead representing pieces of syntax， so E here represents an expression。

 and it can be either an integer I or a subexpression E1 followed by a binary operator。

 followed by a sub expressionpression E2。Or an expression E that is itself in parentheses。

The colon colon equals and the vertical bar that I've drawn in a different color here are pieces of meta syntax。

 They are not part of the syntax of the source language itself。

 They don't go in calculator expressions。 They are what I'm using to help describe the syntax of the language。

Now， of course， if you were ever trying to describe the syntax of a language that did have colon and colon equals or vertical R in it。

 then you'd have to be a little more careful to distinguish between which occurrences of that is syntax versus metayntax。

 but we don't have that problem with the calculator language here， and frankly in most places。

 intelligent readers can figure this out for themselves。Okay。

 so then we also had binary operators and integers as part of this language。

 binary operators could be plus or times， integers。

 I'm leaving as an undefined set of tokens when I'm writing down this grammar。

 of course when I create the Leer I need to define what that said。

So writing a grammar in this way is called Backus Now form B in F。

 and you're going to see B and F all kinds of places。

 I've been using it silently this whole semester to explain the syntax of Omo to you anyway。😡。

And it's used in many other places， you will find descriptions of all kinds of languages with VNM。

Back us an hour are two people who won the Turing Award。

Bakas won it in 1977 for profound influential and lasting contributions to the design of practical high level programming systems。

Ner won it in 2005 for fundamental contributions to programming language design they together invented what we now call B and F when they were working on a programming language called Algll back in 1960。

 So one thing to notice is that the AST and the B and F correspond quite closely to one another。😡。

So in the grammar， the B& F， we have expressions that can either be integers or binary operators or parenthesized expressions。

 and in the AST type we have constructors for the first two of those integers and binary operators。😡。

We don't represent the third because that is a piece of concrete syntax that we don't need anymore when we've abstracted to just a tree。

Likewise in the B&F， we had plus or times for binary operators and we ended up with a type in our AST for representing plus in times as well。

So there's usually going to be this very close correspondence between the grammar， the B&F。

And the AST that you design for the language。Going back to the MLY file we created。😡。

We had a declaration in it that said the starting point for parsing was the rule named Prague。

 which we chose ourselves。And we annotated that with the return type。

 the Ocal type that would be returned by parsing after that we had some production rules that corresponded more or less to the rules in the grammar that I just showed you。

So every rule had the form name， colon， and some vertical bars。

A bunch of productions that could be part of it。And then an action in curly braces that's sometimes called a semantic action。

 but that's a little confusing because it's we're not doing semantic analysis here。

 so I'm just going to call it an action。This is very similar to how a B&F will have a meta variableable name。

 colon colon equals， and then a bunch of productions separated by vertical bars。

Now the main difference is that in the MLY file， we actually add in those actions in curly braces that say what to return as the OcaM will result as opposed to just what constitutes a legal expression in the language。



![](img/a48edeb9edf1f364e26411e6a43c86cb_1.png)

![](img/a48edeb9edf1f364e26411e6a43c86cb_2.png)

So let's look at one of those rules， we had a rule for parsing experts。

 and this corresponds more or less to a B&F rule that would say E colon colon equals either an integer I or E1 times E2 or E1 plus E2 or E in parentheses。



![](img/a48edeb9edf1f364e26411e6a43c86cb_4.png)

![](img/a48edeb9edf1f364e26411e6a43c86cb_5.png)

So here we do have to worry about that concrete syntax because those parentheses are going to come in as tokens from the token stream。

 and we have to say how to parse them。Why do we not have a single rule for binary operators here？

This gets into the technical details of how parsse generators work。

 it tends to work better when you inline them like this， I'm not going to go into it here。

 but you can take CS4120 if you want to learn all about this。

So the first part of the production here was for integers that parsed an int all capitals token that carried an integer I。

 we returned an AST node also carrying that integer I。The next production had an expression， times。

 and another expression that parsed an expression followed by a times token。

 followed by another expression。And we bound the result of parsing the first expression to an oamml variable E1。

 we bound the result of parsing the second expression to an ocaml variable E2。

And then we constructed an AST node to return as the action。

 and that AST node was a binop node with Mlt E1 and E2 in it。Same for plus。 And then for parentheses。

 we kind of discarded the parentheses。 We no longer needed the concrete syntax werere just representing abstract syntax now and returned the expression either。

Finally， the very highest level rule here was for parsing a program， we parsed an entire expression。

 and then that had to be the end of the file or the end of the token stream there。

 the end of the string that we were parsing。

![](img/a48edeb9edf1f364e26411e6a43c86cb_7.png)