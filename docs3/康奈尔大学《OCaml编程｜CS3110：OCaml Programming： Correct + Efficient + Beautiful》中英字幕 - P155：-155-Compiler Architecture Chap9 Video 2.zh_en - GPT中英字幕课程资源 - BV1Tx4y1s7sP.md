# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P155：-155-Compiler Architecture Chap9 Video 2.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

When we look at a compiler or an interpreter。The architecture typically has two big pieces to it。

There's phases of compilation， we say。The front end of a compiler has the job of translating the source code of that language。

Into a data structure called an abstract syntax tree or an AST。Then typically。

 a front end will go on and do some transformations to that AST。 In fact。

 it'll typically rewrite it a few times， maybe even many times into progressively simpler and simpler kinds of representations of the program。

😡，Those are called intermediate representations or IRs。😡。

The back end of a compiler then has the job of translating some intermediate representation into machine code。

So the benefit of factoring a compiler to these two phases is that you can have a well identified intermediate representation that becomes the boundary between the two of them。

😡，That means you could compile many different source languages down to that one IR。

And then have that backend out of that one IR target many different assembly languages， maybe MIPS。

 maybe X86， and so forth。😡，An interpreter is typically not going to have a back end because it doesn't try to translate to machine code。

 it just tries to execute the program。😡，And in fact。

 often an interpreter might not even have any meaningful IRs。😡，Regardless。

 the front end of a compiler and interpreter is largely the same。

And there are three pieces to that architecture。So we can subdivide the front end into a Lexer and a parser and then another piece that doesn't really have a good name。

 but the job of the Leer is to do what's called lexical analysis。

 the job of the parser is to do what's called syntactic analysis。

 and then the final piece of it is semantic analysis。

Let's take a look at what each of those means in more detail。😡。

Suppose that you start with a source program， looks like this。

 it's part of the implementation perhaps of a factorial function in OCMl。

We can think of that as what the human programmer typed in as a character stream。

 they were typing individual characters on their keyboard。We run that through a Leir。

And the job of the Leer is to divide that character stream up into what's called a token stream。

So think of a token here as being a meaningful unit of symbols in the source language。

So lexical analysis， then I like to think of it as just dividing a character stream up into words。

You know metaphorhorically speaking， these are the words of the source language。

The next step in the front end is to take that token stream and to run it through the parser。

The parser's job then is to transform the token stream into an abstract syntax tree or an AST。

So this gives more structure。To the data， it's a different data structure， right。

 We're actually producing a tree data structure out of a list data structure with the parser。

And that tree shows the kind of hierarchical ordering of the program。😡。

This program is an if thin else expression， and so we have a node at the top of the tree that represents if then else。

And we have three subtrees， one for the guard。

![](img/97a46c4327e434193429581add992146_1.png)

One for the Zen branch and one for the else branch。



![](img/97a46c4327e434193429581add992146_3.png)

And each of those has some structure as well。In the guard。

 we're using a binary operator to compare to sub expressionions。In the else branch。

 we're using a function application。And that has a particular function fat that's being applied to a sub expression。

That sub expressionpress involves subtraction。Now notice one really interesting thing that happens here with parsing。

We got rid of the parentheses。

![](img/97a46c4327e434193429581add992146_5.png)

They were there in the token stream to indicate exactly how we wanted the code to be parsed。

We wanted fact to be applied to the entire sub expression x minus1， not just to x。

 which is why we had to write the parentheses。😡，Well。

 the tree implicitly represents that grouping with that subexpression。

By having the minus x and1 as a subte of the apply， rather than just X。



![](img/97a46c4327e434193429581add992146_7.png)

So part of the job of parsing is to recognize how the programmer wanted to group expressions and then put them into the tree appropriately。

😡，Now that we have an abstract syntax tree， the next phase of the front end is semantic analysis。

This broadly speaking， is the task of determining whether the program is semantically meaningful。😡。

And here semantics is exactly what we've been talking about all along with static semantics。

 and that includes type checking。So as part of semantic analysis。

 a front end will typically create what's called a symbol table。

 this is just a dictionary that maps identifiers to their types。

 there might be more to a symbol table than that depending on the programming language。

 but that's its main job。😡，Semantic analysis might go ahead at that point and produce a new abstract syntaxt tree that decorates each AST node with its type。

 and there are more pieces to semantic analysis as well， for example you know that in Ocal。

 not only do we do type checking， but there is an analysis done of pattern matchingshing to see whether it's exhaustive or has any branches that could never be reached Java also does additional semantic analysis。

 things like initialization of fields。So that's all broadly part of this piece of compilation。

What happens next？Kind of depends on whether we're looking at a compiler or an interpreter。

And it depends on the language and the architecture as well。

We might translate the ASD into an intermediate representation。

And then an interpreter could execute that IR or maybe it'll just directly execute the ASD。

A compiler though， is going to start translating the AST into more and more machine like representations。

😡，For more of what that means， you'll need to take a computer architecture or systems programming class like CS 3410。

 we're not going to go into that。Functional languages are really well suited to implementing compilers and interpreters。

It's very easy to represent these tree data structures in a functional language using variant types。

And the compilation and execution of those can be easily defined by pattern matching on trees。

So we're going to see how to do this next。

![](img/97a46c4327e434193429581add992146_9.png)