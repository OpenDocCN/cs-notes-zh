# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p02 P2 -BV1qBqPBYEy1_p2-

然后来。对他人呢。Yeah， okay。So。我现在 come。Tritable chips， eventually。Like nothing is currently working。

Just terrifying。Right。I。Because it's like already。お様。そうで。し最。I don's like too really shared。う。使。这个。

那我这。发给你个。出来听。我几时清楚系。Synthesis time would not be drastic affected。还是。It I。

It seems like this like the facts。goodYeah much yet。is there money items so。いい。Yeah， so at。哎这色的。

That's right。Yeah， that's I'm saying what's the usual program？Okay， so let's resume。

So I left you last week。With the simple expression。InIning the As。

And the two exercises so we looked at。The expression interprets are the simple statements of they home it's nothing and then I left。

Control flow in the lab assignment any。Questions， concerns， comments on the live assignments。

 who managed to get the second one started。Great。Okay。

So let's wrap up this section on AST interpretation and then we'll move on to Bcodes。

So we looked at control flow and I said， you know it's easy in some cases。

Where the control flow you're emulating is。Memics bias a similar control structure。

the implementation language， but sometimes it's also in。

 so suppose we have you know we're implementing we had earlier do or while open we're implementing a break。

 you know， why can't we implement it like this？In break by break。Okay， so it's funny。

 but why is it funny？You're bringing out the switch team exactly we're kind of a little removed from where we need to be so if we want to be that so I'm writing a sort of a sketch of how the function call structure looks well we're interpreting one of these so I use these funky brackets here to den know you know the AST。

Containing this fragment of code， I would use the proper strategyy brackets， so I couldn't find。

So I use this funyons instead。So if we are evaling a do while with a break in the middle。

 then that becomes a do while with in the middle of an eval of a break。

 and then finally we get to eval a break。Wwhichch is going to eval all of the statements in the sequence before we get there and then if we call break。

 well that brake is supposed to come out of this loop so and where like functions removed so that's not going to work。

Too bad because it was clean。So what do you do， Well， unfortunately， that there's no nice solution。

 It just kind of gets messy。 There' there's two。Two approaches here。

 One is to change the return type so that you can。Break out of something early and say I'm not giving you a value back because we broke out of this early and here's the value you have to pass up to whatever is catching it。

 if it's an exception type structure in this case， you don't need that。 you just need。

To indicate that the control flow is breaking out。 and eventually。

 the the that's interpreting the loop has to say， oh， you broke out。

So that's a long way of doing it and it gets messy because you have to know the things that did return a value like expression evalus is have to return a pair that says。

 here's the value of the expression and here's an extra booleion saying whether we broke out of the sub thing。

That we were evaluating， so Soda gets it pervas your code with this sort of drag。

Passing around pairs。The alternative is kind of。What we did earlier which is use the host language and in this case you can't use brick。

 you have to use something a bit more sophisticated and so in C you could use set jump and long jump。

Anyone not familiar with set Ju Long jump and say everyone。搞回来各。Okay， so in this example， you know。

 I included the headerophile and I make one of these magic things that jump off and then in the middle of the loop。

In the middle of the interpretation， I do this call to if set junk。Which is， you know。

 and SeJM has this funny convention which I've forgotten about businesss all long since I use it。

 which is if you break out of the loop using long jump， then you get back a non zeroro value。

Which is confusing because。Break cab using a zero property。

 so here what will happen is we'll go through this statement this will return zero on the first call of Saint jump it will evaluate。

The statement that will evaluate the sequence that will evaluate down to the break will be coming back around in this loop。

And we'll hit the long jump， and that will control transfer。

Transferport control back to the set jump except at this time we're a non zero value。

 and we'll just get the whole loop and go ahead。So。

 so that's that's how one way of least of implementing it。And see if you are doing it in Java。

 you'd probably use exceptions。So in this case， I've kind of sketched the implementation of。

AB in Java and that's using throwing a break exception in the interpretation of break node。

And catching it in the interpretation of。So we do a tri catch of a break exception。

 We evaluate the statement that eventually will。琴 down here啊。

Which will result in a throw and the throw will be caught at the loop。All thisす all thisす。Now the。

Can think of any problems doing it this way？So exceptions are meant to be。Exceptional。And。

Most JVMs with exception throwing catching is really slow。

And so to use it for break will cost you a lot in time。When if you break out of loops。

 it will be like orders of magnitude。More expensive than you would like it to be。

 So it's easy to ride， but it's really slim。So that's one of the problems and hard to really come up with a better scheme rather than passing out the Bo ends and the pairs。

嗯。So in general， what's the performance of our AST interpreter like has anyone actually got numbers for interpretation and measured？

Anything yet no。So well， what does it take to interpret a simple thing like？

B equals two times a plus1 Well， you've got this whole tree of Eval calls as we're reducing the expression to its constituent parts and calling Eval recursively or EvalS if we were doing the statement level and so for this simple expression。

We're doing one，2， three， four， five， six， seven， sorry six356 calls to Evalal plus the actual work that it was meant to do a multiplication and an addition and an assignment that's the part that we're meant to be doing right Evalal is just overhead。

And so， there's a。All these calls， there's a stack depth of four frames of the deepest part。

And every single eval。Is you know， a switch and a tank fetch。And a return。And the call overhead。 So。

 so this is really painful。 The performances is。Is bad， and。In a little while。

 I'll show you that it's along stamping curve machine coverage。

We'll get back to that when we' is the end of the section。诶。

What about memory requirements of this technique？Well， so。

AT these terms of representation for programs are really big。

 especially if you're on a 64 B machine because the point you've got all its pointers everywhere。

 you have the past that you really care about， the representations of the opera and the operas。

And the tokens but you also have this vast number of pointers so anyone remember if you have a binary tree。

 how many what fraction of the nodes are interior nodes？half a tree， half a binary tree is interior。

So in a binary tree representation is of one of these expressions for every interior I know。

 you got two pointers if you're on 64 bit machineless。

16 bytes right there and just the pointers and then it's probably。

 you know there's an overhead for the malloc space that youll you and the alignments and the headers and everything so this。

 it's a very inefficient space representation of code。

It takes a lot of space when you're actually traversing it for interpretation。

 that's also painful because it's like a random walk through memory more or less。

 you know unless the tree has been laid out very carefully in memory。嗯。You know。

 if it just got sort of randomly created and allocated as the program has being passed。

 then you've got all these interactionss you're following。

 many of which will result in cache methods。 and so the loads going through got of directions are very painful。

You can address that by。Very careful placement and design。

 both of us actually can be addressed at some effort。

 one is to instead of having pointers for the interior node of the trade。

You just have indices into a table and you can make that table smaller。

With the width of the indices much smaller so you know if you're not not going to have more than say 64K nodes。

 then you can have a 16 bit index and you can compress the size in if you do a copy of the tree using a depth thrust reversal。

 then the copy will end up pretty linear relative to the original and so when you walk it。

It'll be almost like a sequential war through memory， which obviates some of the cache effects。啊。

And if you want to distribute your IR as a tree form。

 you have to do some of this anyway because when you send it to somebody else。

 you can't send pointers right because they don't mean anything on the target machine。

 you have to build indices and tables and you have to flatten the thing out into some kind of canonical representation which get sent anyway so you kind of have to implement all of that anyway。

 if you're serializing the IR， but the damn side， the unfortunate side is that it's very rare that people distribute。

AT is a form， usually you either get soil on bike parentss and ASTs for a variety of reasons have never really caught on as a distribution format。

So in conclusion。It's slow， It's easy， but it's slow。

Partly because the callinging overhead and the dispatching overhead is very big。

The trees themselves if implemented in the obvious direct fashion are really big。

But it's really easys right and it's easy really really easy to reason about and it's very portable。

 so these those are good reasons and typically when someone implements a language for the first time。

 they'll write an AST interpret person of。Or a simple compiler。

 but if it's not a language mean political compilation。

 or if you don't want to invest in writing a compiler and youre not a portable interpreter using these things really。

 it's probably an easiest thing youll get other than you know a tool the read and semantics and generates an implementation for you。

嗯。So。Usually source code is the distribution medium for people running on AST interprets。

And there are all sorts of pros and cons about distributing source code。

 many of which are non technicalchnized， it's all about whether you think you have rights to access to the source or whether you hide the source and we can get all political if we go down that particular direction so I'm not going to go there。

 but you can understand that you know there are lots of reasons why you might want to do it one of the one way or the other and there's some interesting variations on the thing。

It was a pay in 1994 from Ba。Michael Frans and others which describes a system that they built for Mac Oon which distributed produced compressed ASTs。

 they basically use the redundancy inherent in an AST to compress down into a very tight efficient distribution format and they use it in monitor places but it never really caught on nonetheless it's an interesting read。

 the papers by the way are all listed in detail。In the bibliography that's in the resources section on Piazza。

By definition， this， this。Form is very tightly coupled to the source language， right。

 the AST structure and the source language。Are almost the same all we've done is to remove the lexical noise and so if you change the language。

 you have to change the interpreter。There's a fragility there in the implementation as languages involved。

One of the reasons ASTs have not caught on is because of that tight coupling of language semantics。

 at least I believe， one of the reasons they have been caught on is the tight coupling of language semantics to the format。

 which means if you change change the language semantics a little bit。

 suddenly you have to change the format and unless you're distributing source。

 it really doesn't make any sense and so what's tended to happen from many language implementations they've adopted a different form which is bycodes and bycodes。

 although they can be coupled to the source language， they usually not as tightly coupled。As this。

 and we'll see when we look through。Bikecode design。

That things are a little loosesome and you can play different games。

So that's the stand of the section on。A Ts， are there any。Questions or comments。

While I take a couple of minutes and just GDP to step through some execution， I I'm about to do that。

action framework州跟石中。Yeah， sure。嗯。Okay， so the way this works is。

You have this pair of things that look like functions in say。

 but they're not really normal functions。ASet jump and long jump。 And you have a。An opaque type。

 a jump off here don't know what's inside it， you don't care。

 it's just declared in this head of file， you make one。

 you declare one and you've got one because you're going to need it。

So you make one of these things and you call set Ju。

And what Se junk does is it if it's the first time it's been called， it just returned zero and says。

 okay， thank you， give me a jump buffer， I'm done， you can carry on executing。Well if a later time。

You call long jump with the same Buffo。Control goes from here。

Back to there as if you came out with here。Okay， even though you already came out of it once。

 you can come out of it again。And the value you get back now is not zero。

 so you can tell whether it's the first time through or a subsequent time through。

And that gives you the ability to do a。what looks like a call from here that comes out as a return from here。

Okay， so， okay， so。I should do the set enough。the Yeah， so E so e is going to our loop。

 our loop is going to evaluate our sequence。 Our statement sequence is going to evaluate break。

 which is going to come here So then the break you do the launch and then you said it's like you return set So then go back to Yeah would you want to go back to Well。

 because you want to you want to go out of this loop。

And what that does is it enables us to come back as if we come out of the loop and we're now before it again so we can ignore it。

 knowing that we came out and everything that was going on inside this eval and inside the eval call from that and inside the eval call from that。

 all that stuff just gets thrown away Sta is un to this point we only go inside of the loop。

 the first time。 Yeah， once we get the break。Yeah， it's kind of weird much。

What it does what you need， so what is the performance of this lake？It's not bad actually。

 it's much better than an exception in Java because you're not making anything。

 there's no allocation involved。And what you don't get to do and see is write exception handlers which have to be checked as the stack is on red so it just cho chops the stack right back to where you are in this function。

 does a little bit of magic with a jump off to restore the stack pointer to where it was as if you were coming back out of there it's pretty quick。

 we're clear though。What clear does the variable are today？Like you get out。

 you have to clear it at some point。Now， when you call set junk with J。

 some magic is dumb involving that very well， it's kind of an interesting exercise to figure out how to implement it。

Because it's a little bit of machine code here and there end dabbling with stack pointers and program cameras。

 but it's actually not hard， it's a handful of lines of code so。这个是Yeah。啊这就。Yes。😊。

This is jumpnking to the AST， so you said that AS2 is bad because it's too much memory right？

It's have like two pointers。 But what if you do this like for the parts of the AST you already took birth and that you no longer need to go to can't you just modify the ATs to get rid of that part Well。

 so the difficult part is knowing that you don't have to go back to it。可 if。

If your AST represents the inside of a function， how can you know that you're never going to call that function again if you're new sure you could do that。

 but in general， the halting problem says you can't do。

You might be able to guess in some circumstances。If you have a function that represents an initializer that the language rules say。

 you're only ever going to call this once， right， by definition， well， then you can pause it。

 run the AST and then throw it away。But with exception special cases like that， you don't know。

So you could always go， but throw the AST away and go back to the source and reppause it if you wanted to regenerate AST but that that's slow。

 right， that's much slower than the interpretation。呃，这。Jay's appointed there， right。

我没 check code I ran。If you have passed my value， I don't think I could write code。In general。

 I run stuff to make sure it really works， and sometimes I get copy past down。很厉害然。ほ。啊，这个去。

In the code I ran， there is no emphasis in the code I ran， there is no emphasis。

That might not be correct， so。jump man， yeah， let me get the。often macros are built in。也是是自己买这。

Sa term is magic， so should necessarily assume。It follows normal rules。6是。这个这。は。Yeah。好啥事。你 okay。

And recent Xcode or something， let me probably will on the way。Um looks like you're right。

 at least my I'm I'm a network because don't someone at yeah， you don't need a point。

Okay so it doesn't follow。Anything that makes any sense。😀ふふ。😊。

And I have written an implementation of it。Its that was 35 years ago， So I don't have to remember。

What it does， but it's magic using SPs and PCs。I think essentially if you're confused。

 you can think of it as just storing and doorstep。That's a natural step。Even when you launch up。

Over right door is that one give store where。那没上法。It's one implementation that usually works is you make a macro which。

Calls a assembly function with the point through your jump path， which saves。

The appropriate thing and does a little manipulation to make the return work。

Itportative languages outside。So。Quion we could be evaluating within multiple do while loops right so in that case we would need a stack for then you would need a different jump buffer for each loop and you'd have to yeah you'd have to somehow figure out how to find the one that was the appropriate level in the same way in the Java code you'd have to somehow label the brake exception with where you were breaking out of and have it you know matched with suitable catch。

The hand record。So it gets kind of messy。I think in Java case。

 the exception would just go to the closest catch， so I think that would be fine。Yeah。

 I mean in you know， yeah， the easy example because usually brake breaks the nearest enclo loop。

 it just sort of folds out nicely if you wanted to have a special break that you could like label the loop you were breaking out on or or in the worst case like a go to a go to would be horrible。

You're going into the interpretation of something that's deep in a tree that you're not going to function anymore。

 so Go whos a real problematic in this world。Okay， what was I going to do？し。To do this。哇。

Should I sense the话。就审法院。You know， I'll figure this out and set it out。During the break weekend。

Subject提。啊。Alright， so let's move on。去。Ex extension。Okay， so what we're going to do next。Hiss。St。

Looking at。The structure of a real virtual machine。And we'll kind of work our way from the top。

Down through it， initially looking at the specification of what it might look like and then as we go through the weeks we'll look more at implementation so we're going to start with specification and rather than look at a fictitious VM I'm going to use the JVM as a concrete example partly because you know it's hugely widely deployed and so you might actually need this information one time if you're building stuff that runs on the JVM or you modify a JVM。

 but it also will give you some sense of the level of complexity and craft。

They encounter are in the real system。So let's start with。the very highest level view。

 what are we going to look at， basically four parts I'm going to decompose the system into。

One is the state that's associated with the execution。

 so there's the explicit state that's part of the interface of the system and that might be the memory。

 heat objects， whatever is implied by the semantics that the VM is implementing and registers if those are exposed or a stack if that's exposed and then there's a bunch of implicit state which is part of the implementation of the VM。

 but that's not part of the specification and that the implementer gets to choose how to structure so the first level we'll just look at the explicit state。

 the part。Put there in the spec。Once you've got the state you then need some way of manipulating the state by execution of instructions。

 and that's the next step is you have a specification for the individual instructions and what they do on the abstract state。

 the part of the specification does and then you have what's really going on under the hood on the real state as it's implemented internally。

And the real execution Ill come in in a laterly look just at the spans on it。Then typically。

 you know you could in theory， sort of do a VM with just these two well it probably wouldn't be much used because you usually need some level of library support some of required functionality beyond the simple execution of instructions to get somewhere so for example。

 you might need the implementations of functions or language features that can't be implemented through the ISA as described。

 you might have operations and functionality which need to be internal and also you might provide just libraries of useful stuff implemented as part of the VM which is maybe more efficient than implementing in the language that you're executing the guest language。

So this is kind of the equivalent of OS traps。On a compiled language。

 right it's the stuff below you that provides the functionality of the environment that you need when you write real applications。

And then the last part is external interfaces， again。

 you could live in a self con world and knocked up to the rest of the world。

 but increasingly that's not。So useful， so you probably need some way of calling out the code that isn't written in the language。

 the guest language of the V that's preexisting in some other language or pre supply binaries。

 shared libraries， things like that。 So you need some kind of what's called a foreign function interface to call kind of it's not part of the BM。

 but that might be useful And so we'll look at each of these in turn。

So the example I'm going to look at specifically is the current Java VM spec。

 I took the document of the website for SEEA， which is the current wall I was just about to be replaced by SE knowing。

And what we'll do is we'll have a look at the abstract there in this section。

And that's reasonably brief， it doesn't take a lot to describe the abstract state of the system。

 then bikecodes and bikecodes just seem to go on forever。

So there's just no way we'll get through them all today。

 we'll start today and you if you're still awake， we'll carry on next week with them。

 but there's just a lot of about。In the JBM。 And it's worth looking at in some amount of detail。

 both to see what goes on sort of in reality to implement a full industrial strength system。

 And also in especially what I'm going to try and do is is highlight the。The what' some good version。

 the craft by the stuff， the stuff that。Just smells bad in the spec It's sort of why is it this way。

 why are these different and seemingly inconsistent choices being made。

 what where are the historical artifacts where some mistake was like hidden and swept under the carpet stuff like that because it's there and it's very plainly visible if you know what to look for in the spec and this serves as kind of a warning to you which is if you ever end up building and writing something like this trying not to make these mistakes because the price for them as being extraordinarily high and we'll get into some specifics as we get to them。

The mistakes。Now I'll have a quick description of libraries and primitives and the JNI。

 you know I'm not going to give you a two of the J libraries we'd be here till the next in thelenium if I did that。

 but you need to know a little bit about how that stuff works in the interfaces of the VM and then a little bit about the JNI which is the way to callrelate to other languages or to call back。

And the spec is available as a download， you can buy the bulk if you want。

 but you can also just download a PDF。From this website and you're probably going to need that for an exercise and some reading。

 if not this week， next week， so go there and grab it when you get a chance。

So I'm going to start kind of with the coarsest step levels and work in。嗯。

I'm going to present things in this kind of pictorial form because I think it's the easiest way to understand what's going on now the spec has all of this spelled out in excruciating detail because that book is like you know 600 pages of thick。

It's there's a lot of detail here now I'm not going to go into all of that detail and I'm going to provide you sort of this conceptual view of the way things work。

 which is sort of the model of execution you know these pictures are like cartoons this isn't really what's going on inside of VM this is the this is the programmer's view of what's going on and the underlying VM is often。

Transforming this into some other much more complex representation to squeeze every last of performance out of the system。

But you can't understand that until you understand what it's trying to do。

 which is why we're with these pictures so let's start f sta。

Java program can contain a bunch of threads， he has a bunch of threads， insurance， boxes。

 each thread contains a program counter and a stack。And maybe or maybe not a native stack。

 the spec is kind of little bad on this。 There may or may not be a native stack。

 It may or may not be intermingled with the original stack。

 but there has to be something in there for when you call out a native code for it to have a stack。

 so it doesn't go into detail。 It just kind of wipes that under ver table and says that's up to the implementer to decide。

The program came to。Is really at this level， you can think of it as a triple。

 as a triple consisting of the current class in which you're executing。

The current method in that class and the bycode offset within that method。

Sometimes the spec talks about it being just a PC and of course in reality in a real system it's implemented as a PC or conceptually the way to think of it is not as a PC because we're at a level of abstraction above PCs and so there aren't any addresses here。

 this is just boxes， at this level it's really that triple。

So within a thread you have the stack stack is made up a set of frames and frame look roughly like this。

 The layout here again is conceptual there's no concrete description of what order things appearing it's just there has to be this stuff in some order for the VM to manipulate so whether the return address is at the bottom of the frame or the top of the frame or whether the stack goes up or down or how wide it is all of that's left to be implementable or it has to have。

They stay for the white code to operate on， so you have to have a return address in whatever form you've chosen to implement。

You have a bunch of local variables which contain the values of the local variables in the corresponding method。

 and then you have an expression stack that can grow to a certain size and you can index these things using the numbers as indicated。

 or at least you can index the local variables using the numbers the stack is usually addressed as top of stack or the thing that's one below the top of stack or the thing that's too below the top of stack。

Okay， so the heap is the thing that contains the objects。

It basically has to contain two different kinds of objects， instances of classes and arrays。

Those are fairly distinct kinds of entities in the spec。

instance of a class has to have some kind of a reference to the class in which it was made and contains the fields that are specified in the class description in some order。

 The order is not actually。Explicit in the spec， you can implement the order and the alignment and the packing however。

But the spec has a way of talking about each field。啊，我我 get了。Succeeding slides。

s are arrays of some common based type。And now the length and that's really about all there is to them and it provides VM provides bikecodes instructions that create these things。

 well there are no bikecodes that destroy them。So that's how you get to automatic memory management and garbage collection。

 you know， the VM just has to do that sort of behind end of the covers and there's no。

Visibility into the detailed operation of that at this level there's just no way of talking about the garbage claim。

Okay， so if we look at an object field。A field or an real that can contain either a reference to another object。

And the size of that reference is implementation dependent it doesn't say anything about whether it's 32 bits or 64 bits or you know whatever that's entirely chosen by the implementer。

 it doesn't contain a reference then it contains some kind of a primitive value and that's a fairly limited primitive value。

There's integers of various sizes from eight to 64 bits。

 and there's IE single and double precision numbers。What does a class look like？Well。

 a class has to contain a bunch of。Things are listed here。

And the way those things are described in a program that's loaded by the JVM is that their entry is in a class file。

 so you when you run I'm sure you know this， but when you run a job of VM。

 it loads classes from class files that in the adult class although。

Embbedded in bigger things like jar files and those class files contain this information and most of the information is in a thing called the constant pool。

 so the constant pool，Is sort of this soup of data structured data that contains either numbers or strings labeled for specific purposes or structures。

That describe things like fields and methods and interfaces and attributes that are made up of structures or that are made up of these numbers or strings。

 so it's just kind of a hierarchical decomposition of the world using structures。

Recursively and numbers and strings and these parts of the class that are more recognizable are really just indices into this constant pool to go through the pointer structures in the constant pool。

 we'll look at some in in some detail。And again， doesn't specify anything about the memory layout of a class。

 how a class looks in memory， just has to represent these things in some way。

So let's look at a simple example on that picture we had。

 so the name of the class is just an index to a string。

 the name of the superclass is an index to a string is a trivial flag so just like，AB of characters。

 so let's start with the description of a field。What does a field specifier look like in class file？

And that gives you some indication of what the VM has to represent when it reads one of these things。

 So the way the spec is written is。It lays out the file as if it were a C str with explicit sizes on the subfields。

 so for example， the access flags associated with a field are a two byte unsed in U to is two by so there's U one and U2 and U4 and maybe U a as well and a few other types。

嗯So。The spec says if you read， you know， you index。

 use the concept pool index for a field descriptor。That will give you an offset into the file。

 the first two partss of the file of the access flags。

 these are the access flags that are available in the spec thegoi detail as to the exact encoding of each one of those。

 you know which one is value zero， which one is value one， etc。

So behind each of these slides is like 50 pages。Of text。

 which I'm trying to save from reading unless you were in a meet him。然。So that's a nice symbol case。

 The name is again， just the string， the descriptor we'll look at on the next slide and it's another structure。

 and then you have attributes that can be associated with each field specification。

 some of which are predefined by the VM and interpreted by the VM， so for example。

 the attribute could be this field starts with a value and the value is a constant and the constant is here in the constant pool。

So all of the index fields for things in the structures that are end in index or into seasons of the con pool。

 that's the way to read this。Yes， what does the JBL need to know about？It's like that disability。

Because as youll see when we get through the bikecodes， it needs some of this。

To enforce access controls。So even though there were certain access control specified in the source。

When you make Y code， nothing stops you from handais in the class file to say what you like。

And so it needs to look at these， check that they're consistent amongst all of various places and check that the access rules are enforced in the bikecode。

Also， there are descriptions of some things which might not be needed for execution。

 but are therefore for reflection because you can reflect on the class and you can ask about things about it as if it were there in almost a source form。

And so it needs to be able to give you those things。Yes。比话。Those parts。

It's verifying that the use of a variable is consistent with the flags with which it's been declared。

多费油。So it is the interpretation in case someone direct bycode of let's say， setting flies are inable。

So， that again what is the interpretation or maybe it's just encode code so it's impossible。

 but what is the interpretation for the。诶。诶。Tpreter， should they have multiple JBM。

 what there's multiple flags that are set that are incompatible。

There are rules that say what the compatibility， you know which things are mutually exclusive。

 which the combinations are valid， and when the class is read， the VM is meant to check。

 that it falls into one of those valid patterns and if it doesn't， it rejects the class file。

Does next。one thing worth pointing out is that nothing in the field description says where it lives in an object。

If you look if you imagine this being the description of a field within an instance。

There is just a name， it doesn't say it's an offset three or a position seven or it has a particular characteristic like that。

 that's all for the VM implementeder to choose。Okay， so。The field descriptors。Descriptor index here。

Field descriptors describe field types， so again there's an encoding of all of the types that are understood。

 the base types that are understood by the JVM a single character。

 so B is a bike he is a cha he is a double， etc， and you'll find in the constant pool there'll be a string or one character string that encodes these all the various types that are required in this class one。

If you have an object type that is the field is' a reference to a certain kind of an object。

 the descriptor associated with that field looks like this string。

 it starts with an L which tells you it's a reference and then the class name is literally followed it followed by a semico so if you look in the class file and I'll show you a tool later that sort of lets you delve into the guts of class files you can see these things laid out。

And then an array type is very similar， except it starts with a left square bracket。

 I think there might be a cneical I that not the end of that。

 but it's a left square bracket and then the I think it's implied by this section that theical left square bracket and then the type of the component of。

So you can see from this that you can tell immediately by decoding what the underlying type of a field and an object。

What they kind of veryical。When it comes to describing code。

 that uses method descriptors and they give you a signature for each method。

And that's sort of like it builds on this。 it's basically a parentheses with a bunch of parameter descriptors。

 each parameter descriptor is。Somewhat like these field descriptors that you have a sequence of them and then there's a return descriptor that describes the return type with V for void is added in that case。

Because you can't have void as a field time。So if you look at a method， typical method， an object。

 my method that takes an in a double and a thread， the descript are in the class file for that will look exactly like this。

It will be left parenthesesis， the I for an n， the D for a double， an L Java slash Lng slash thread。

 which is the type of the third parameter the semicolon。Cluse brand assess。

 and then the return type is object， which is spelled out fully as juggle land object。

And youll see when you delve into class law， obviously it's all over the place。Okay。

 let's not one level of complexity to methods how does a method look in a class file well again it's a structure with a bunch of indices into the class pool。

 so you have the access flags on the method with the appropriate set of encodings provided for whether it's public or private or static or flavors。

You have the name， a descriptor， which I just had on the previous slide。

 and then you can have this arbitrary number of attributes。

 some of which are recognized by the VM so you can IDs can kind of drop random extra amount of information into the attributes which is just there as like commentary from the point of view of the VM you can get access to it programmatically through an AP。

But it doesn't have any meaning， but some of them have a meaning to the VM。 And in particular。

 the attribute called code is the thing where bikecode is stored。 So that's a really important one。

 iss no no other place to put the bike codes other than in the code attribute。

So if you want to explore， there are a number of kind of nice little interactive。

Class file viewers in which you can use to introspect because you know。

 it's just a super binary information， which if you just list it out。Andd of looks meaningless。

But if you download it here is one I picked it almost at random， it seems to work fine。

 you fire up this little Java application， you load a class into it。

 it shows you the binary representation of the class。

 but then it also shows you on the side all of the various components of that class file and when you click on one it will highlight the corresponding bytes in the file and you can kind of see that they make sense and look at the encoding in the book and see that it matches the file you compile original if you have the source for it and it's somewhat instructive to get this tool and sort of tool around with some class files and just see how it looks inside。

 see if you can navigate the structures in the spec by navigating the corresponding components in the view。

Okay， so I mentioned the code attribute。So the code of a method is held in its code attribute。

 I hope the font is picking enough to see it back。And this is the biggest one that's a list。

 so this is the most complicated and it has a bunch of different bi fields。

So the obvious thing is the man and the length。啊。And then there are a bunch of things that are related to the actual the code and how it operates。

 So there's a number that says the maximum depth。Of the expression stack in the execution of this method。

 And that means the VM has an idea of how much space to allocate in a frame when it's executing。

This曼。It has the maximum number of locals that are in the method， so it can index and no。

 if a bycode says it wants access local5， but the max locals is4。

 then that's illegal because there isn't anything if there isn't head allocated throughout local。

It gives the length of the code and then the code is just a bunch of bond。

And we'll go through the bikecodes in the next section on JVM。

Then there's a structure called the exception table， which we'll look out towards the end of that。

That describes how exceptions are executed。And then another section of attributes and the attributes on code。

 there are several that are used by the VM， for example。

 there a line number table that maps pieces of the bike code to the corresponding of source lines that they were compiled from and obviously that has no。

Semantic meaning to the execution of the program by a debugging environment that connects to a VM when you want to debug will want to relate where you're at in a method to the source and that's the way it does it this table has to be emititted by the compiler with the correct line boundaries't it。

这很。Really it bikecodes back to the source and there's another important structure which we'll cover probably next week called stack map。

Which are used in verification。Briefly， the Bcode ISA breaks down into a bunch of different sort of subcategories。

There's the obvious stuff around arithmetic， addition division， et cetera。

 a variety of athmetic types。There's a memory access。U and object creation， bycodes。

 you can make objects， you can make arrays， you can access the fields。

 you can access statics and classes， you can access the locals in a frame。

You can do stack manipulation because this is a stack machine。

 so there's no notion of register in this ISA。Everything is done by pushing and popping things from a stack and manipulating the values on the top of the stack。

 so you need stack manipulation things to pop unwanted values or to pop a value。

 install store it or to swap the top two values and there's a bunch ofarrow。

Then there's bikecodes to do various type checking conversion operations within the rules that are specified by Java and a large number of bikecodes that are involved with control。

 so from the basics of doing things like simple comparisons of values and simple branches based on comparisons。

Through。Five flavors of method called。And then obviously you need return as well as coal and then there's a whole bunch of stuff around exceptions and exception handling and we'll go through this。

In excerruciating detail。Starting later。So I said every VM has to have some set of proms。

Sometimes known is intrinsics， intrinsics often used by the compiler community to imply an operation that could be written in the language。

 but that actually is just kind of immediately implemented。

The two there's kind of a fuzzy line between these two books basically things that have to be implemented。

 but that you can't express out in the language or maybe the expression would be so slow that you wouldn't want to do it like that and there are a handful examples and not surprisingly many of them are in object。

So get class。Is a built in primitive that returns a reference to the class of an object。clone。

 clones an object， hash code gives you the system generates hash code underlying。

And there's an alias to that called System I Ha code and every JM has to provide an implementation of about these and many other such things for it to actually be a valid job。

Implementation， you can't just implement the bikecodes。

 you have to do all this stuff too the way you can't run anything useful。嗯。

Can any of them be written in Java is a little quiz question？没事。

So the spec of hash code is kind of loose， which is。Any number you like。As long as it's constant。

For each object， so you could trivially write that inja you and return to round。

 that would be a valid。Clone， I think， could be written， I think using reflection， but it's really。

边薄。Do you have question， I did have a question。So。There are other designs for VMs where like。

 so this design is you have your bike set and you have like these special objects。

 which you can look at as if it weren't regular objects。

Would you can' actually write yourself so that system revise it。

But then there are other R VMs where it just provides a special bike。Do special instruction before。

 right and then when you port to the。So that's one of the sort of interesting and potentially curious design points。

In this spec is the choice of things they decide to make。

Primitives that are just have to be implemented by the VM are method level and the things that are there by。

As you see when we look through the bikecodes， the bikecode itself is very irregular in the way it's been designed and this is another aspect of that irregularity。

And you know， I can't give you a good reason why it looks like this because you know I wasn't there at the time。

 but it's sort of an instructive exercise to think about all of these things in entirety and think。

 well what could have been a bikecode， why wasn't it a biketecode？

Or why wasn't a bikecode made into a primitive method， you know。

 it's worth looking to see where the distinctions lie。Yes， so if I get this the reason I have。

Ficient and because there's so many objects。 And if you want all of them to have the。

Then better to do bikecodes because bycode。Well， so hash code in a normal implementation is actually quite efficient because it's not doing any hashing at all。

 it's usually using the address of the object of some other system generated thing which is fairly efficient。

 and it can give you that quickly with the right properties。

 basically you want hash codes to be very evenly distributed so that when you use them as indices into hash tables。

 you don't get lots of collisions。So if you use the system implementation。

 it has because of its knowledge of the underlying storage management。

 the information to give you a good hash code quickly。If you were to write it in Java。

You could write one， but it wouldn't be a good one and if you wrote one that give you a quick hash code。

 it would be a really bad one。 So this is one of the examples where in theory。

 you could do this at the Java level， but in practice。

 you really want the VM to implement this because it can do a much better job it efficiently。

What is like what's definition， Why do you need reflection。like sign each bill。 Well。

 so you so clone operates on any object， right， you can say if X is a reference to an object。

 you say x do clone and I'll make you a clone。Now you could write a clone method for every class。

That made a clone of instances of that class。 so this is one method that can clone anything。

So we're saying like we're basically trying to write it on the base object class so that yeah。

 so everything can be cloneed。But you can't write a method that clones any class。

 any subclass of object without using reflection because you don't know what the fields are， right。

 an object。You have no knowledge of that， you have to use reflection to get access to the field structureses。

Please remember that question for your next assignment。我你感。If you had G class。

 can you just use clone on G class， knew of that？羡慕啊。Well， it seems like if you had Git class。

 you had， I mean， get the class in the object， clone thatgr called new of the Git class object。

Well that gives you a new class， that doesn't give you a clone in the instance。

 or then you have to fill in the member variable。How do you do that。

 you still need to get an enumeration of the variables somehow。Okay。

When Me calls are executed in normal and a normal Java program。

 some of them are in the class lives in Bcode， some of them are native so making this decision and switching from native to things that are implemented in the Bcode does that have a significant performances so in general。

 the stuff that's implemented as native。Within the VM is much more efficient。

Because when the VM sees that bycode， you'll see when we get into compilation。

 it will just substitute。The inlined code of the definition of that operation right there。

 that usually isn't even a call overhead。 So hash code often isn't even a call。

 It's just a few instructions that get inserted into the instruction string So so that's one of the reasons why people push stuff into primitives and intrinsics。

 It makes them more efficient and some of that's kind of you know it's a little dubious in that you're making an efficiency decision at the cost of some flexibility because now the Java code that was the original thing is being ignored and if if you substituted a different Java definition it would to have no effect。

So things like some of the mathematical， complex mathematical operations have been made intrinsics。

 even though there's a perfectly good Java implementation available to get performance。

 so you look at the Java code and you think， oh I know how this works and I can change it and I can do something different but it has no effect at all because the actual implementation is deep in the VM and it's using that one。

 not the one that's there in the class file。Yes。So I just thought I get this right。

 So the reason I get classes better than bike code is because in the bike code for every authors。

 we have like the fields， right。Well， so in this case。

 we have one method that can return the class of any。Object， even if it's a subclass of objects。

 so it can't know about all of the subclasses because some of those you haven't been created yet。

So to write something that does that in one method in Java is impossible。

 you can't come up with a description of that in Java code。

 not using gett class and so that function is provided directly by the V end because when it has a reference to an object。

 it also has a reference to the class。From this picture。

first thing usually in an object is a reference to the class that it came from and so when you call get class。

 it just returns this field。Well this field isn't in the source code， you can't access this field。

Using the source code。You can write dot class， which is sort of like it。

 but that's really just a short answer for。For that class， right， you can't do class equals。不大会这个商。

Okay， last couple of slides， and then we'll take a break。So I talked about primitives。

 these are things that the VM really sort of has to implement either for necessary functionality of performance。

There are also libraries that typically come with an implementation that just provide you with a bundle of useful stuff that makes the language more usable than if they weren't there and so Java has you know a truckload of these things that come in the platform that provided as part of the system and that some of them are known about by the VM because they're actually implemented inside the VM so for example。

 one of the things you can do in Java is you can manipulate files using a file API without knowing what the underlying operating system is。

 so there's kind of abstracts away from the OS below you。

And gives you the opportunity to manipulate files without having to write directly to Posss or win 32 or some other API that the OS is providing。

And it gives you a portable platform neutral interface。

 and you can see all of these things from the Java IO package are described as native methods。

 so you won't find Java code。In the JDK for these， these are implemented in C or C++ in the VM and there'll be multiple copies of those implementations for all of the different file systems that you can run the JVM on so the implementer has to deal with that part problem。

 not the end user and there's a whole bunch of this stuff with natives that basically abstract away from the underlying platform and that makes Java programs that bit more portable。

So you can think of this as the Java A is the whitecode set plus the collection of these standard API is available because that's sort of the set of services that you get to sit upon。

 not the one below it， which is the native instruction set and the operating systems A this is a level above that and isolate it somewhat from it。

d确审落方。And then the last part of the external interface I want to mention is the Java native interface。

 and this is the thing that allows Java programmers to call out to libraries written in other languages or for those libraries to call into the PM。

and do stuff so there's a level of interoperability there's an assumption in JNI that kind of sees the lowest common denominator here and so it talks about the C ABIs。

 which is usually the case on most systems that see is the bottom of everything anyway。

So theres a sort of there's as sw towards C as the external language but most other languages have C interfaces so that isn't in practice a big problem This is a in itself。

 you think of this as a simple facility right， you declare a function。

 you pass some parameterss you call it。You're done right， How hard can he be。

There's a whole book on this section， right，300 pages on this alone。

It's a vast amount of detail because it's actually quite ambitious。

 it's trying to give you a way of calling to an external library in such a way that you don't bind in any of the specifics of that library other than the names of the things that you're calling you can substitute a different implementation of the same shared library as long as it has the same functionality it will work。

 you can use multiple different Vs。To call out to these libraries and the code it'll all work on all of them because it isolates you from the details of the VM internals So for example。

 when you pass a reference to a Java object to your C function。

 you're not really passing a reference because that would expose the internals of the JVM you're passing an reference to an indirect I think all happened So there's layers upon layers of stuff to kind of decouple the two sides and that's what this whole book is about why this interface is so complex and what that bites you doesn't handle like interaction。

Java call and C calling back that same Java and that and forth you even you can even invoke a job of the end from this Kevin right exactly a multiple Java of the end so it's very so rather than go through you know masses and masses of code explaining how to write a G&I operation I need the two minute sketch。

 which is this is roughly what you have to do。In J and I to call an external native method。

 you start by in Java， you declare the method that you want to call as a native in your class。

 so you write signature for it and it a native for one of the keywords and then Java says。

 okay I don't need a body and I'll trust student there's one out there。You then use Java H。要。啊。我。W。嗯。

You give it the name of your class file， and it generates a C header file。

For the natives that were mentioned in that class file， so it basically says， okay。

 this is the signature in your seat code that you have to implement。

For me to be able to call you a function。 So usually that does not correspond to the thing you want to call。

 So you then have to populate that as a wrappper calling the real thing。Blow it。

 because this header is written in terms of the C description of Java types and not a C type。

So then you write a C file where you include j。ahh。

 which predefinines a bunch of stuff for you and the generated header that you've got out of Java H。

And you fill in all of those functions with C code， doing whatever is the appropriate thing。

 like calling the real function that you want to get to。You then compile your C into a library。

 a DLL or an SO or whatever， and then in your Java code， you go back to the original thing。

You put in a call to systemload library naming the library。

 you just generated it and you have to set up your paths and everything to make sure that it finds it。

A few， once you've done all that， you can memoryor the Java program。

 it will invoke a system load library that will load the thing you compile from C and the things will。

 if youve got it all right will make beautifully and you'll be able to call out to your C program。

The sad part is the path length through that interface is really quite long。

 so you don't want to be calling very simple functions at the end because you'll be completely swamped by the overhead of going through that barrier。

 which is probably thousands of cycles。嗯。And it's a massive thing because not only does it allow you to call functions。

 but it allows you to access data， it allows C to call into the JBM and it allows it to access objects without messing with the garbage collector。

Create instances， invoke， Java methods， all sorts of stuff。啊。And I will leave it at there。

We will take a。15 minute break and I will get GDV that helps just give you a quick demonstration duration of stepping through the expression until。

喺你。Question。One last question， if you're using something like J and I， can the C code。

Break some assumptions about the VM state within the it can always break anything because you know。

 it basically it's trying to designed in such a way that，Unless you are malevolent。Or really。

 really stupid。And sometimes there's a fine line between you unless one of those then it will try to isolate you from the most obvious mistakes so that you don't inadvertently say corrupt the Java heap or cause the garbage collected to crash or whatever。

But if you try， you know， if you take a pointer and you start making a point into random places and sort of poking stuff at the end of the pointer。

 yeah， sure， you can bring them。We built years ago as an experimental thing some an implementation of J& I that actually put the called library in a separate process。

And use an inter process call to do that， which is horribly slow。

But it's a great way of finding which side of the line the bug is on when something crashes。

 because if it dies on the sea side。Now it's your problem。

 it's not the JVM implementer's problem anymore， you go away and fix your sync code。

 whereas if it dies on the JVM side， then it might be a JVM。But yeah， in general， yeah。

 you can always break stuff。Okay，15 minutes。Back up 300。Point Eval。

 And I've run the program to there。 So we're now suspended Eval。

 And then then what I've done is I've set it to display the current instruction。

 which which is something everyone should have at their fingertips by the end of this course in whatever the debugger of your choices。

 which is that expression in G B。 So thats says every time I。Get back to the prompt。

 it's going to display the value of the current PC as an executable instruction。嗯。

Now I showed you that because it's in general useful in this particular example it isn't useful because I compiled this with the optimizer turned on to minimize know make it as efficient as it could be。

 so we actually get no source visible so that's really not going to do as any use in this particular case。

 but in general when you're debugging particularly Jit compiled code。

 you will need to see the instructions that you're executing and this is the way to do it is something like that。

Then in GDB， you can type next I， which runs the next instruction as opposed to the next line of seaau。

And displays whatever it's gonna display， which in this case I've got two displays turned on。

 but it doesn't matter。 And now， if I hit return， it'll run in each instruction one at a time so we can kind of count how long it takes us before we get to the printf。

I know what this number is。 So I'm gonna go through it real fast and not expect you to keep up counting。

 but you'll see how long it it， it is。 So that's1，2。10。😔。

You can see the evals coming up as we step into functions。Somewhere around now， we should get。😔。

An answer。Look at the 19。So discount。We're back in Maine。 So that was it。

 And we should get those than 19。It's about 120 instructions， if you were counting。What should？

A equals 2 B plus 1。Actually， take efficiently。A load。A multiply an ad， an edo。Okay。

 so that gives you some idea of how inefficient this is。 Were a hundred and 25 versus 4。

So we're a long way off。 And， and some of the many of these are calls， right。

 which are and loads through a tree and stuff like that， which are expensive。

 So that gives you some idea of the， the performance loss。

That we're incurring by doing ST interpretation。Some of the things you'll have to think about in the exercise are you know。

 how many in machine instructions are you you executing per interpreted node。

 something I want you to think about is if you're， you know。

 underlying architecture and things about branch predictors。

 What's the predictability of the control flow through your program。

Look at the source that you write and if you were to predict how it was going to execute。

 how would you do that， what do you need to know to predict the execution of your interpreter？

Undo good branch prediction in the machine code。And how many loads does it take just to walk the tree of a simple example。

 Those those are good things to look at and consider as you're debugging your program。Okay， section4。

And this will set you up hopefully for the next exercise after AS T interpretation。

 So now we're going to cover bikecodes and bikecode interpretation， as I mentioned earlier。

 ASTs and AsT interpreters are easy to write， but they're really slow and the interpreter is very strongly tied to the source language semantics。

 which can be a bad thing。And so。In practice， bikecodes seem to have taken taken over the world。

 And so it's worth looking at what are bikecodes， How do you design a bikecode set。

 How do you interpret a bikecode set， and then in future lectures we'll look at how you compile bikecodes。

So the problems I enumerated with ASTs of size and behavior。

 you know real machines don't have that when they run normal machine code and so someone kind of lost in the mists of time back in the 50s or the 60s thought。

 well， why don't we just mimic a real machine in the instructions that we're going to execute？

And rather than do this AST interpretation stuff， and maybe that will work better。

There's literature about this， but it's not clear that the literature begins with the invention。

 It seemed like it was kind of in the air at the time。

But we'll look at some of the literature in a later lecture。

So what you end up doing is you design an instruction set architecture for the language that you're interpreting or some approximation to that language you're interpreting。

 If you make it exactly the same。 then you get back to this problem of coupling。

 So you want to make things a little looser and you'll see as we go through the example。

 it's not so hard to be loose in that respect。 Now real machines expose a whole bunch of details which have to be dealt with the hardware level。

 which you don't need to deal with in a virtual machine。

 And so a virtual machine implementation of an ISA typically will abstract a away a whole bunch of these choices and kind of you know wave its hands at them。

 just designed with that tour of the JVM spec where I said， you know。

 there's a thread it lives somewhere， it has a stackg， the stack lives somewhere。

 but the spec doesn't list all of that stuff out that's for the implementer to choose。

So you want to omit details from the IS S aspect by by abstraction， typically。

 So the address of a variable on the stack， if you。

 if your language can't take the address of variables。

 you don't have to expose addresses as a type in your virtual machine。 So you can。

 you can cut corners that way and make the spec more abstract， which makes the。

Programs that are compiled to it less tied to any specific implementation。

 And so one common choice is to use a stack to manipulate expressions as opposed to registers。

 So you pushche values and pop them from a stack and you operate on the stack。

 And that has the benefit that you don't have to do register allocation in your language implementation。

 which is kind of a pain。 It's a complex thing to get right。

 And and you don't know how many registers are on the real machine that you're running on anyway。

 So how do you pick a number that's good there。 you know， one is a good number。

 but that's not much of a register allocator more than that。

 it's hard to know what a good choice would be。Especially， you know。

 in the world of old when there was more than one architecture in commercial use。嗯。So。

So let's run through an example。 And rather than running through a real example。

 I'll start with toy1， which is our expression language and how we might make a bycode machine to execute our expression language and then compile the bytecodes and interpret those biketecodes。

 So we'll start with our expression language which obviously just manipulates integers。

 So the machine model is easy。 We just have a stack of events。And when we see a variable， we push。

 sorry， when we see an integer constant， we push the constant onto the stack。

 And when we see a variable， we push the variable onto a stack。And when we see an operation。

 we execute the operation， so we'll have a bike code for each of the four hourrithmetic operations。

 and that just pops the top two values， applies the operation。

 and then pushes the result back on the stack。And we might want to also be able to pop the stack into a variable for an assignment。

 So that's kind of a very small， simple bikecode set。 Looks like it would cover what we need。

And it gives us a nice sort of abstract description。

 Now we this course isn't called abstract machines for various historical reasons。

 but it's probably in some ways a better name than virtual machine because that's really what you're trying to do in the design of of a machine for a programming language is to abstract away from the hardware。

 But you also have to supply unfortunately， some tedious concrete details that make it not so abstract。

 Now there have been abstract machines proposed and described in the literature。

 and they're usually really abstract in that some of them are just described in papers。

 there is no implementation or if there is an implementation。

 it was never used to actually run real programs or applications。

 It was just used as a demonstration kind of thing。

 So there's a whole bunch of things that you can find in the literature。

 know the granddaddy of them all， really is the tuuring machine， but you know。

 go by your infinite tape if you can find one。 There are these others in the literature。Many of them。

 I've just pulled out a couple of examples that were well known in the 60s through 80s。

 SECD machine for executing Lada calculus expressions， I think dates from the 60s。

And there was a prologue abstract machine that was actually the basis of many prologue implementations and was called an abstract machine and not a virtual machine。

 interestingly enough。 But you do need some details， which are unfortunately not abstract。 So。

 for example， if you're going to actually send your instructions to somebody else。

 you have to pick an encoding， and this encoding has really nothing to do with a language It's not nice thing you can abstract over。

 you actually needs to pick an encoding。 and you need to pick formats and things。

 So you end up with something that's like well， a concrete abstract machine， which you know。

 sort of a bit not not really a nice term。 So virtual machine is the term that's stuck in this area。

 and and there is a definition， the dictionary definition。

 which which is you know kind of does really correspond fairly well to what we're doing。

 So it's not physically existing as such made by software to a appearO。So virtual machine it is。

 but there is there is an extensive literature on abstract machines。 And in the bibliography。

 there's a survey paper on lots and lots of abstract machines that have been proposed over the years。

So here's， a possible bikecode design for our expression language I've。

Deliberately picked names for the op codes that are not the same as the names of the tags in the A S T tree just to avoid any confusion there。

 And Ill I'll maintain that illusion for a little while。 But eventually it gets tedious。

 and I'll drop it。 and I'll use the same names。 So what I've what we've done here is we've designed a bike code set in which there are eight instructions。

Con nice convenient number。 Most by codes are 1 by containing3 Bs to describe the opera end and 5 bit。

 sorry，3 bits to describe the op code and 5 bits to describe the operaand。 Remember。

 we only execute programs with single letter variable name。

 So you can get your variable in notaught to 25。 So that fits in 5 bits。

So the only exceptions of the one byte rule is the first byte code， which is a literal。

 which which pushes four byte of integer onto the stack。

 Then we have a single bytes to specify additional subtraction multiplication and division and we don't use the the lower five bits of each job code and then get and put which read and write from a variable and the lower5 bits then are index into some kind of variable structure。

 and then we have an end byte code。 just to end the program。 you'll see why。

 why that's there hopefully when we get to it。Now， how do you go from expressions into bikecodes who's familiar with reverse Polish notation。

Oh， good。 good。 Who has a calculator that works in reverse polish。Times have changed。

Once upon a time， all calculators operated in that film。

So reverse Polish is this form where you take a normal form of the expression with in fixed notation and you write it with the operator following the operaran。

 So in this case， two times a is written as2 a times。

And2 times a plus1 is 2 a times1 plus because we're adding the result of the two times a and to the1。

And then you've got some interesting choice as to how you do the assignment。 you've got various。

 it depends really on what your abstraction is here。

 You can think of the assignment as a single assignment to to a variable， you know。

 as sort of a single operation that does a store to a named place。

 or you can think of it as pushing an address and then having some kind of a store operation。

 But that's for this purpose， for this particular example。

 that's not good because we don't really want to expose addresses as another type。

 just we just want ints as our type。So another form is to push the name of the variable and then have the assignment operator operate on the name of the variable and the the value that's being stored。

 And that's kind of how we're， we're doing it in this example。

 And you can easily generate this form from the A S T。

By basically a left or right depth first walk of the A T。

 So if you think about this A S T with the exception of the assignment。

 when you walk this left or right， you go down， you do two， then a your depth first。

 So you do the leaves before you do the node 2 a times1 plus and that gives you the reverse Polish for the expression and then for an assignment because there's an order here and you want to value it the right and side before you do the assignment。

 you have to do the right before you do the assignment and and a compiler can easily generate the sequence。

Of op codes here by that simple walk。 And， and one of the exercises， I think， is to do this。

 Is't it for。Do we do a bikecode generator in the exercises， or did we drop that。Okay， cool。

 So you will， you will have to do this for F。From the IDs。So， I a simple expression。

Which is this S T looks like this sequence of operations and hopefully。

That's straightforward and easy to understand， push2， get a and push it on the stack。

 multiply the top two stack items， replace with a result， push one。

 multi add the two top two stack items， which is the result of the multiplication and the one。

 replace those with a result and then put that result back into B。Very simple。A。

If you want to compile them， as I said， it's fairly straightforward and here， in fact。

 is a very simple recursive function that does walks the tree and emits the the bike codes。

 what I've done here is I've I've omitted the definitions of a couple of support functions。

 so emit byte。Takes。A single byte and adds it onto the stream。

 That's the output stream and emit word text4 bytes and puts those in the output stream in whatever indianness we decide we we want。

But otherwise， it's a straightforward recursive A S T walk that takes an expression。

Dispatches on the type of expression。 If it's a constant。

 it just emits a bite containing the lit instruction and then passes that。Result to emit word。

 which emits the， the， the 4 byte value。 if it's a variable。We just do a get。

Which we bit wise or with the the， the index of the variable。 If it's an ad。

 we just emit the ad after emitting the sub expressions right and then left。Oh sorry。

 left and then right。And then for an assignment， we do the right hand side and then we emit the put that puts the result into the variable。

So that's very straightforward and it's written in a slightly stylized form because one of the things I can do with this in C is I can type de。

Output to be either a car star and have it appending to a string in emitmit byte and emitmit word。

 or I can type def it to a file star and have it writing to a file。

And the same code works on both of those。 So it's kind of。Almost meadatic in its form。

So I'll let you stare at that for a while。 Any questions on。On that， or is that straightforward。

Let is。The name of this instruction。So each instruction has three bets。With a unique value。

 And the way I encode those is， I have。A macro。That takes this number and just shifts it left 5 Bs to give us。

The the value。Yeah， always just a shift left55。 In fact， I've got it。There we go。Sorry。

 I should put that those definitions up first。 So O just takes the up and shift it left by5 to put it up in the high bits。

Now for the interpreter， we have to pick apart the instructions。

 I have the corresponding two macros that pick out the high3 bits and the lower order of 5 bits from the。

 And I just used that。 And here's the bikecode interpreter。

Which is expanded out into all its gory detail。 So I've like you wouldn't normally write it like this。

 I'll show you how you would normally write it on on the next slide。

 But this is intended to kind of capture， you know， all of the， the gory detail all in one slide。

 So you can see this sort of no magic going on here。

 So all we've got for a bycode interpreter here is an infinite loop。😊。

Notice that here's where we need our end instruction to break out of the loop。

We're just dispatching on the high order 3 bits of the next bite。For each bite。

We then have a case matching the corresponding op code。

 and then we do the actions associated with that。 So for a literal。

 we take the next four bytes of the instruction stream。 So that's PC 1， PC 2， PC 3 and PC 4。

 and we you know， combine them all into a 32 B value。 and we push that onto the stack。

And then we increment the program counter by 5 because this is a 5 B instruction。For add。

 we take the top stack element and we just add it to the the one below it and then we decrement the stack and increment the program counts because it's a one by instruction。

 Similarlyly for subtract and multiply and divide those are all follow the same pattern。

TheThe line that gets a value from a variable just takes the five lo bits of the instruction。

 slices the indexes a vasear array， which I haven't shown here。 it's just the simple int vase 26。

And then pushes that onto the stack。 And the put is the inverse of that。

 So we pop a value from the stack and we push it into the corresponding variable。 It's very simple。

Any questions？Okay， so we want。We want an instruction set in which every operation。 Well。

 most of the operations are one by long。So we have five bits that we need to allocate for the variable name and three bits for the op code out of the8。

 and we could put them anywhere we like， but I chose to put the op code in the high order 3 bits。

So you have to do the shift。To put it in when you're writing the file and the opposite shift or masks to get it out。

Note that。Even though this is an interpreter， I've done a little bit of work to try and minimize overhead here。

 So， for example。Rather than taking the by and taking those higher order three bits and shifting them and then doing a case。

 I just match against constants， which have them preshifted up。To save on that operation。

And in general， is written fairly tightly， minimal。

Additional arithmetic that wouldn't be eliminated by a decency compiler， at least。Yeah。嗯。I wasn't。

 but I could。 I'd have to find a thing at the next break and compile it。 Oh， I do have a version。

 yeah。You'll probably end up stepping through yours when you do the Fiie version。Good question。

 so I mean， I those a five examples here。Yes， yes so you don't want to write something like this。

 even if it were a simple byte code set like this because you've exposed all of the gory detail here know and if you change the slightest thing now。

 So for example， if if if I make all the instructions to bytes I have to go through and edit every line of this or if you know my stack changes in layout。

 What you want to do is add a little bit of abstraction。

 just a little probably through macros are in line functions。

 just to decouple you a little bit from the details and to make it a bit more readable So in this which is closer to what you'd write in a real implementation I've written push and pop as macros that do the star plus plus SP starP minus minus stuff because you don't want to change every occurrence of those。

If for example， you're on account how many pushes an expression is doing you're on a simple way of annotating that rather than having to dive in and modify every line and I've added simple macros to do program counter increments and and to convert you know pieces of the instruction stream into literals So this is this kind of a sketch of more of what you'd really want it to look like。

 something a bit more tiny bit more abstract than that really you know。Very literal example。Okay。

 so that's a very simple bycode interpreter for an expression language， which has no control。

 What happens if we add simple conditionals and loops。

So let's consider if we have conditional expressions and simple while loops of this form。

 and I'm gonna。Stipulate that comparisons only appear in control expressions。

 So you can't put them on the right hand side of an assignment。

So what we do to implement something like this is we have very similar to the way you do it in a physical machine。

 you add bike codes to implement comparisons and branches， so for example BQ BLT。

 which do look at the top two values on the stack， pop and compare them and then branch or not to it by a given displacement based on the outcome of the comparison。

Weson need an unconditional branch。Which doesn't manipulate the stack at all so that we can implement the backwards branch at the the end of the loop。

 and we still haven't exposed the PC as something that's maniptable。 right。

 There is a PC implied in the spec of this machine， because we have bikecodes。

 but there's no way to access it。 That's a choice we made to abstract away from that。

So what would it look like if you compiled a conditional？

You'd end up with a sequence like this in the output。

 So if x equals Y would compile to a couple of gapts on x and y。

And then branch around the then part and then the then part。

A branch around the else part and then the else part and a couple of labels。

 And you would have to in your compiler， fill in these offsets， right。

 That's actually the hardest part of writing a compiler for something like this is the is the back patching of the。

 the offsets。cause you have to obviously do that otherwise， you know， bad things will happen。

And then for a loop of the while we've got a similar code for the conditional。

 a branch around the body in in the case that the conditional fails。

 notice that you have to invert the sense of the condition to do this if you execute it in in the way it was order it was written。

And then for the assignment， it's the straightforward， you know gap。

Literal add and put before we go back to the beginning of the loop。

What's it like to implement these in the interpreter， Well， simple。

 unlike the control flow in the AST interpreter， which can get horrible。嗯。

Control flow in the bycode interpreter is easy because it's。

 it's just the program counter you're manipulating。So B。

 here's an example of what B Q would look like。So we've got the branch displacement is encoded into the instruction in this example。

 So， okay， now I've changed the instructions。 I've added one。 So now three bit encoding won't work。

And our 8 bit encoding won't work unless I have fewer than 26 letters。 So I would have to。

 at this point， reencode the entire instruction set。

 And if I'd had literally plus plus PC everywhere。 all of those would have to change into， you know。

 something else， probably。 So you have to imagine all that because I'm not going to spell it all out in detail。

 But for this to work， we need we need a different encoding。

 and I'm going to use the lower  four bits of the branch instruction and the following 8 bits as the displacement for the bytecode jump。

 So for a B Q， we pop the two top stack elements。 We compare them。If they match。

 then we increment the PC by the displacement， which is coming out of this bikecode and the next bikecode。

 And I'm adding two on。 Can anyone guess why the plus2 is there。Yes。But about afterwards。

You lower8 bits of your。Yeah， yeah。 So I've just chosen arbitrarily here that a branch of 0 goes to。

The next instruction， it's an arbitrary choice。 I could have chosen 0 to be anywhere I like in this displacement。

 I could have had branch 0 branch to itself。So， you know。

 it's up to you when you design the bike codes what you choose for your encodings and you're entirely free to do out you like。

 as long as you make the compiler match， of course。嗯。Okay， so if， if they're not equal。

 then we just skip over though。The， the instruction to the next instruction and unconditional branch is even simpler。

 It just branches to the displacement specified in the instruction。um。

Why did I choose not to take the displacement from the stack because we have a stack of ins？

And I could have put the displacement on the stack。

 and I could just be branching to whatever integer is on the top of the stack。Yes。ピザ。

To prepares and not brands。Okay， okay， yeah， that's a valid reason， yes。Reition。Yeah， that's。

 that's sort of more to it， which is。In this language， we only have structured control flow。

 We don't have arbitrary control flow。 And so we don't need arbitrary computed jumps in our in our bikecode set。

 And if you put them in， then it gets kind of really difficult to debug because you know you sort of you don't know where the branch is going to go until you run the program and so figuring out what the program is going to do without running it is somewhat more challenging。

 So you know it's just an example of making life easier for yourself in the design of the bikecode set。

 it would work either way it would just be a little bit more exciting。The other way， yes。

Since it doesn't matter。12 up to0。こと彼である。It's just an it's an arbitrary choice。 I I， I could。Yeah。

 yeah， yeah。 I could have chosen not to do it。And it probably doesn't make much difference in this case because the plus two probably it would get hoisted out by a compiler。

I the health also shift。Yes， it must。 It must。 Yeah， good point。ピせこス。嗯哼。Okay。

 I didn't run this part of the code。 so is buggy。Okay。Oh， the other room。

Good reason why not to have the computed go to is when you come to compile。The bike codes。

If you have a computer， go to now compiling it gets much。

 much harder because now every branch can go anywhere。

And you really don't want that in the compiled code。So， having。

Static known control flow structure in the bike code will be important when we compile。Okay。

 last twist， I think in this bycode set is let's look at what it takes to add functions and call them and return。

 So we're going to extend our trivial little language to have single letter functions uppercase so we don't confuse them with the variables。

And here are some examples。 So we have simple expressions。 and you can even do recursion。

 So I've put the tacky Ui function， a favourite of compiler writers at the end。

 which is a nested recursive thing。嗯。So here's the sorts of expressions that you might want to compile。

 Now we need to extend our model a little bit because we have no model for for functions。Now。

 we could go down the path of rayfin a PC and a stack and stack pointers and all of that。 But again。

 from the point of view of abstraction， you really don't want to do that。 You want the call you know。

 in the abstract form， the call just takes the name of the function you're calling right It doesnt You don't want to assign numbers to all of these things and have those encoded into the into the program。

 just have the name right there。 So we're gonna have an op code。Whi has says call n。

 where n is the number of parameters we're passing， and it has as an argument。

 the name of the function that we're going to call， which is the upper case letter。

 why why did I put the the number into the call rather than making that value on the top of the stack。

Anyone see difficulty if we go down the other path of putting the parameter on the top of the stack。

Yes。Orizations for example highlight。Yeah， it just just makes it harder to see what's going on Staically。

 you want to kind of expose as much static information as you can get from for when you want to compile。

 So if there were a variable there， we， we couldn't compile a call because we wouldn't know how many parameters we were passing。

 It would get really messy to do that。 You'd basically have to have a little sort of interpreter or interpreting the stack。

Okay， so the， this part， this op code is gonna take the top end。Stack items。

And it's going to call the function in some frame of its own in its own stack。

 And when the function returns， we're going to replace the top end items with， with a result。

And the return link is implicit。 You know， it's the there are just words saying that the call will go somewhere and it will come back。

 There isn't anything explicit in the bike code or the model here。

So the frame needs to store the arguments， but so then we need some way of getting at the arguments if we're going to have you know lexical nesting。

 So what I'm going to do here is that there' will be an indexed submar in each frame for the arguments and we'll use L get and an L put to access them so。

Here's a picture。So here's the kind of the logical view。

 And this is very similar in some respects to the Java picture I drew you before。

 And we're in the middle of one of these tay Uhi recursive calls here。 So here's the original frame。

 It has three local variables。And it points to something that represents the body of the function knows about the number of local variables。

 And here are the bike codes for the function。 So the function just takes。

Pramatters and pushes them does a comparison。 And if you compare this with the tacky Ui code。

 you'll see it corresponds to the the tacky Uche body。

First thing you do is this comparison and branch and if not then you you have some more arithmetic and eventually a call。

 so I haven't shown the whole thing out because it would get really big。

 but if we're in the middle of one of those subcas。

 then that frame would be on the stack too and it would have some indication of where it was called from。

 it would have some indication of where in the bikecode stream it was called from。Sorry。

 this is its PC。 This is the， the function here。 the PC here points somewhere else。

 and then it has its own local variables and its own stack。

So we have to make a choice now how we represent the function in bycodes。

And there are a lot of choices here， depending on how we go， you know。

 a lot depends on whether our VM is set up to read source and execute it。

 whether the bikecodes is just an internal artifact or whether it's ingesting some kind of binary representation。

 We're ingesting binary representations。 then we have to specify a particular layout in the file of how the bikecodes look for a function and the function structure。

 And that was really， you know the JVM spec has that in spades in how how you structure a whole program into binary。

 the source string version just doesn't constrain us at all we can do what we like in that case。

If we go down the path of making functions， values are allowing reflection。

 then that gives us more things that we have to think about and more structure that we have to expose at some level。

 But let's do the simple version。So。Here's the state before a call， with a frame。

And we have this is how we're gonna implement it in the Cla in the code that comes on the following slides。

 We're gonna have a frame pointer that points to the base of the frame。

The stacker points to the current top of stack， so the arguments will be at the top of the stack。

The return address for this frame will be saved somewhere and there'll be a saved frame point of which we're going to return restore when we return。

And then our call sequence is。We're gonna push another frame and adjust the pointers to all match。

 So if we get this picture right， it should。Should look like that。 Okay， so if I go hot between them。

 the F P and the FP pop up。 and then the thing that was the F P pointing down here goes into the saved F P。

So that we can restore it when we do a return。And in this case， we， we're punning on the stack。

 If you notice， I'm not doing anything with the arguments other than moving the stack pointer。

And the frame pointer。 So I don't have to copy the arguments。 I'm just using them in place。

 in this case。So what were arguments become the local variables of the called function in this example。

 And that's a fairly common trick in interpreter implementation。What does that look like in C code。

Again， it's pretty straightforward。 It's a little tricky。 There's a lot of detail。 but， most of。

 you know， most of V Ms is detail， not difficulty。 So you just have to make sure that the detail is。

 is right。 So here's the implementation of call 1， which passes one argument。

I'm using a local here just to carry the number of arguments。And you push the frame pointer。

 you calculate a new frame pointer based on the number of arguments you've got。

 you push the return address。 Remember it has to be plus two because you don't want to return to the call instruction。

 You want to return to the instruction after the call。嗯。Interesting question。

 What's the type now of the。internalnal stack pointer。What， what must it be？

It's got to be capable of accommodating a pointer now， because we're pushing。

 we're pushing a PC onto the stack。 and a PC was declared as a， you know， a cha style earlier on。

 So now we can't restrict the stack to containing just in values of a certain size。

 It has to be big enough to store。To store。Addresses as well。 So that I haven't。

 I've alllied that detail。 But that's something that's important now in the choice of the。

 the design of the stack。It's now got wider， probably。And then I have a， you know。

 a little structure accessing thing that I've wrapped up and labelled as given。

 given a program counter， you know， the name of a function。

 find me the entry point of that function as a program counter。

 and and that's how our new program counter。 And that's where we'll start executing from。

So that's call。 When we're in the function to get our variables now。

 we're just indexing off the frame pointer。Cause the frame pointer points directly to the base of the frame。

 And that's where the the arguments are。 So we just have to pull out the。

 the appropriate index from the instruction and push that onto the stack。

 And then the return just does all of this in reverse。 you know， undoing the stack。 So question 2。

 what's on the stack when we get to a return。I'll show you the picture。Yeah， we're in。

 we're in this state， so。What we're going to do is。And we're going to pop the return。

 the return value is here， right， because it's the last expression。 and we want to move it to here。

Cause that's where it's going to be needed in the cold frame。

So we're gonna pop off the value and write it into F P 0， which is the slot at the bottom。 This guy。

 this is F P 0。So this goes into here。Then we pop off the return address because that was the only thing on the stack in this language。

 it assumes that when you reach the end of a function， there's one value on the stack。

So we can pop the return address。Wops， run way。So that goes into PC。

 And then we restore the frame pointer and the stack pointer from the， from the appropriate places。

 And off we go。So that's a simple implementation of call and return。 and this does work。

 This is this code that's been。Pistted from a running version。 So should work。I'm sorry。本そで演在。

As to local。Yeah， El Ga0 is L v 0。So these are the local variables。

So if you have the only type I'll get。Then you'll get the saved frame pointer。 Yeah， yeah， Well。

 that's。 So that brings us to a question， which I've been。Punting on for some time。

 which is the validity of the bike code relative to the validity of the source program。

 And that's sort of a big thing， at least in Java。 And we'll get to that in some detail。Yes。

I thought we were。Yeah。are。反是。Well， so you don't know， because this is in C And C doesn't tell you。

 C says ints are the size of an en is machine dependent and the size of a pointer is the machine dependent。

But whatever you do， you're going to have to make sure that in this implementation。

 each stack element can accommodate the ints as big as you want for this programme。

 for this language and pointers because we're pushing pointers onto the stack now。

I could have done this using offsets if I'd have identified a common offset。

 a common base for all the bikecode and had offsets from that。

 And that might have saved me that problem。 But that's a decision you have to make when you're designing your virtual machine set and your instruction set。

 What， What are you gonna。What are you gonna store in the stack， an encoding or the literal pointer。

 And if you're storing a literal pointer， then you need space with pointers。Okay。

 let's close up the section so Im。This was a straightforward function calling sequence where there's just a simple correspondence between name and function in most languages it gets more complicated。

 And in particular， if you look at object oriented languages。

There there's a fairly involved process in going from the name of the thing you're trying to call to the thing itself and figuring out where the PC is。

And if you've not been through the implementation of an object oriented language。

 I wanted to spell it out in some detail because a lot of the optimizations we'll look at in subsequent sections willll be trying to make this go fast。

So in an old language， typically you have some kind of identifier that names the method you're calling。

 a name or maybe a signature。You have in your hand an object to which you're going to apply that method known as this or self or whatever it is dependent on your specific language。

And that pair uniquely determines the method you're going to call。

 but you have to run through these steps to find it。

 So you go through from the receiver of the method to the this reference to the class that implements that。

 and then you search that class's methods for one that matches the name or the signature。

 depending on the language smantics。 If you don't find it in that class。

 you go to the classs super class and you keep searching as you go up the hierarchy。

If you're in a dynamic language， you might get to the top and still not a founder in which case it's an error。

 and you have to somehow signal an error often by calling some other standard error handling method。

But either way， if you find the method， then youve you've got to do an invocation and this is a this is a lengthy process and if you were to do this every time you executed a call。

 your implementation would be very， very， very slow indeed。

 And so a lot of the techniques we'll look at coming up will be how to how to make this go quicker。

The final topic I'm going to cover on bikecode staff is serialization because in practice。

 once you've got a bikecode instruction set， it's a fairly straightforward thing to design a file format for it and then use that as a way of distributing programs and you get into this comfortable spot where you you distribute programs which are portable a machine independent so you can run them。

 but they're not source And so you haven't given away the source， you know。

 having to deal with distribution of source And so it's been a fairly popular。

Way to go for many language implementations。 And there's a good example of that in new Eax。 You can。

 you write an Eax list and you can compile their Emax list into compiled files and distribute those independently of the source。

 But it's a very common pairing of。Source files and compiled a by code。

So you find lots of languages good down this path， Java or being one of them。

Notice that we have once youre distributing bycode and then interface to a virtual machine。

 This is goes back to what you were asking earlier。

 We've introduced now states in the virtual machine that can never be reached from the source language。

 right， We can do things at the VM level that have no。Expression at source level。

 And so you have to decide。Whether that's important。

If you care whether people write programs at the bikecode level that potentially violate assumptions that you could make at the source level。

 but that you cannot make at the bikecode level。 So， for example。You know， the targets of the calls。

 right， you call a function that isn't declared。 You can branch to a bike code that isn't there。

 There are all that you can push things or pop things。

 You can pop a stack until it's empty and keep popping it。What does that mean， Now。

 you might just legitimately say， well， you're stupid for doing that。 You know。

 the programme crashes with some horrible error。 It's your problem。

And that's a perfectly valid answer。😊，In the right context。 but in some context。

 it's not the right answer。 So one of the design points of Java was that it was able to ingest class files from elsewhere that had been written and that weren't trusted。

 and that would， in some sense， validateate them for a certain set of structural properties before it random。

 And so in that case， that's probably the most extreme case。

 it goes through a whole bunch of checks to make sure that certain assumptions are never violated in running bikecode。

 But it's an important design decision when you're designing your bikecode set is you know。

 what's legal and what isn't legal。 And when it isn't legal， what are you going to do about it。

 Are you just going crash Do you have to report an error。Yeah。

 so are you going to go talk about how you eliminate a lot of these checks？

So obviously if you're checking everything。Well， I'll， I'll show you how the JVM does it。

 which is to do it once。And then never during execution。

 And that's the general solution to this is to， is to， to have a verification pass。Yeah。

 but we'll go into that。So you have to， at least， you know。

Decide what you want to do or defend against it。 if you think it's， it's a defensible thing。So you。

 I think you've got enough now to。Go ahead and do exercise 3。

Which is to do the bikecode interpreter for Fi。 I don't whether you want to talk about that yet or whether you want to leave that for next week。

We have a lot of more。嗯。Days and days worth。Okay， okay， and then I have some slides on performance。

 And we'll go into those a little bit after I think you've done some implementation of bikecodes'cause I think it will make more sense then。

 So this is a good point to stop。And take a break， I think。

We can begin looking at JVM bikecodes briefly。 We'll take a 10 minute break and then look at some JVM bikecodes。

 But there's a lot of JVM bikecodes。 So we'll be doing that for quite a long time next week。

Any questions？With Java， you help the bike for that being too。

Does the JPM convert that to an internal bycode， which has been interpret？

And later we compiled that to light。No， no， it interprets directly what's distributed。

 or it compiles it directly to machine code。 There's no other form that's being interpreted。公回で。Yeah。

 so， so， so there's a process of resolution there that converts the strings into indices or pointers under the covers。

 and then it cachees those and uses those later。 And there are little hints of that。

 especially in earlier versions of the DVM spec。 It talked about some of that explicitly， but we'll。

 we'll look at the techniques in some detail。Yeah。Okay，4，30。

And we'll go for one half hour before we're done。And I could use more water。Thank you。だか。

Anying Mexican。政ばいな。说个你个样本名。Notpparently that。家清信。有啥？いやそうです。デ在感。と曲。Okay。

 so we're going to start looking at the JVM Bcode set in a second。

 but that's it's a really big and complex bikecode set。

 so it's going to take us probably all of next week to do that too。

But one of the things I wanted you to do before next week is read this paper by James Gosling。

 there's a full reference in the bibliography file in the resources section on Piazza including a link to the SCM Digital Library webp page。

 so I assume you all have。DL access to get the P DF of that。 If you have a problem， let me know。

 I'll， I'll。I won't say on record。嗯。But that's the only part I want you to read this week next week after we've gone through much more of the spec。

 I'll want you to read the chapter that's about compiling for the spec。

 and then there'll be this exercise on sketching a design for an alternate bikecode set but this won't make much sense now so this is for next week。

So I'll go back to the first slide。the second bullet。The yeah。

 the second bullet is next week's exercise。 and the other part of the reading is next week's exercise。

 just， so just to reiterate it's。The jams gozzling paper。Compiling sorry， Gosling 95。

 and it's called。It's called。Java intermediate bikecodes。And it's a 1995 publication from a workshop。

So it gives you a good insight into the original design centre for the Java bycode spec。opposed。エクちゃ。

So there is a if you go to the resources section on Piazza。

 there's a bibliography that I update every week。And the reading is in the bibliography。

 So if you see Gosling 95， find the paper by James Gosling in 1995。 And that's the one。No。

 you don't have to read that this week。Yeah， just the paper。 It's， it's a short and easy read。

 So it's not a lot of work to read that。Whoops， wrong one。Okay， so we're going to take。

A look in a some detail at the bycode ISO， we've already looked at the state an abstract level。

 the threads， the heap， the structure of the class files， how to navigate the class files。

 and there's masses of detail that sort of you can drill down into if you need to see that。

 but I don't see any point in going through all of those structures in detail。 it's kind of tedious。

The bikecode set。Is really big also and takes a long time to examine in detail。

 but I think it's more interesting to look at in some detail because of the sort of the historical impact of this particular design and also some of the strange decisions and features that were made。

 some of which are strange only until you understand why they're there and some of them are strange。

 even when you've finished understanding them。 So it's worth looking at sort of all of the quirks in some level of detail。

 So this is going to take us， you know the remaining half far or plus probably most of next week。

So here was the categorization I put up earlier into five categories and the way I'm going to run through is I've just copied and pasted sections out of the manual。

Into the slides。 And I've highlighted the bits that we're going to talk about。

 and I've put some annotations on the slides， and I will talk about them。 And we go。

 we start from the simplest stuff about， which there's not very much to say。

 and we'll get more and more complex as we go through the set。

 So let's start with arithmetic arithmetic is easy。

 There's really very little thats surprising in the bike code set。For arithmetic。 So there's。

 there's a lot of arithmetic bycodes。 Perhaps that's the most surprising thing is just how many there are。

 And， you know， the reason for the profusion of them is that they're typed。

So there's an instruction ad， a long ad， a floating point ad， and a double floating point ad。

 and that pattern is replicated through almost all of the bikecodes。 There's an instruction。

 long float double variant of each one。And as you go through。

 you'll see that pretty much straightforwardly。 Then you get into the shifts。

 which have both signed and unsigned shifts。In to the right and logic logical and arithmetic shifts。

 And then you have bitwiddling stuff， which is all fairly straightforward on longs and ints。

 a simple this kind of doesn't really belong in this section。 This is increment a local variable。

 It would be better off in the local variable section in my， my opinion， but whatever。

And the only part that looks a little funny is these comparison instructions on floats and doubles。

 and there's basically two variants for comparisons to deal with what you do with Nans there's sort of these little corner cases in the Ipoli spec for doing one thing or another when you meet Nans。

 whether they compare as you know incomparable or whether it's an error and's obscure details。

 which I don't remember even though I read that page yesterday。

 So so you know that's the the only reason I've highlighted is's kind of the only part of this page which is un surprising。

Does the job。She why。The Java programmer can specify which one of these exact FP in the specification of a function or an operation。

 and that's basically mirrored in the bycode choice。

And all of that was done at the behest of Professor Kahan， which is。Of legend es statusus。In't their。

We'll get to that。Good， good observation。 keen eye。 That's what I'm looking for。 It's like。

 why did they do that。Okay， so then you look at the individual specifications of each。Op code。

 and this is what it looks like。 So we look at one of them in some detail。 So， you know。

 I have to pass the page and then we'll skip the detail and look at the salient features。

 So this is the。I add into your ad instruction。 all of them layout like this。 and you have operation。

 a quick description of the operation。 You have a strange little boxed picture as if that was to convey something to you。

Then then you have a form which gives you the specific encoding of the bytecode。

 So you know that this is Btecode 96。 And then there's a little schematic of the stack before and after the operation。

 So an ad takes two values from the stack and it replaces them with a result。

 That's how you read these fairly straightforward。And then there's the textual description exactly of what it does。

 So you know， it's it's supposed to be very preciseable value and value value1 and value 2 must be of type n。

 The value is a part。 The result is the sum。 The result is pushed on the opera and stack。

 The result is the 32 low order bits of the true mathematical result in a sufficiently wide twos complement format represented as a value of type end。

So。So interestingly，32 B ins， they're baked into the VM at this level。 That's what ints are32 B。

If overflow occurs， then the sign of the result may not be the same as the sign of the mathematical sum of the two values。

 I I was really， I couldn't find figure an example in which they weren't why it says may and not will not。

 But maybe one of you guys knows your numerics better than how I do。um。

And then there are never exceptions from overflow and underflow。

 So ints are just 32 B wrapping ins and sort of says everything you need to know about I add。

F add is kind of the same， except there's all this， you know。

 gr you from all the variants of nauns and infinities and zeros of opposite sign and all of that stuff。

 which I'm not going to go into。 There's like two pages of the stuff。 So， so， you know。

 whatever it does， it does what I every Ipoli 7，5，4 says it's supposed to do。

 But the format of the description is just the same。And the same applies to long a。

 So long ad looks like I add。 but now it's talking about 64 low order bits of the true mathematical results。

 longs are 64 bits baked in。Into this VM。And we'll talk about some interesting consequences on the stack now。

 because you notice the stack picture has two values going to one value。

 and the earlier stack picture had two values going to one value。

 But the earlier one had 32 B values。 and this has 64 B values。So you have to。

IDon't wonder what's going on there。And double looks like the flow ad。

 but with doubles substituted and all the usual weird cases。 So I won't go into that。

 but it's all fairly unsurprising。 And all the other arithmetic instructions kind of follow this pattern。

And they're all unsurprising。 So we， we're done with， you know， that' saved you 100 pages right away。

Let's go on to something a little more interesting。

 So load and store load and store in in the JVM is not what you think。

 Los and stores are actually only to local variables on the stack。

Stuff that hardware people would call loads in stores are different。If they called something else。

So these are transfer between local variables in the opera and stack of a frame and I showed you a picture of a frame before which had an opera and stack and local variables and there are variety of encodings here the ones with the index bake in。

 there are ones that have an index as as a field and there are all the various types longs and ints and floats and doubles there's a load which is now a reference load。

 so in addition to numeric types you can get references to objects and so a is the prefixed use for reference in the JVM spec。

There are the inverses， which are the stores all corresponding to the loads。

 There's a lot of variances of trying to get constants onto the stack from various different sources。

 and then a funny one， which we look at called wide。So let's look at the， the highlighted ones。

So we'll start with a load。So that introduces to us a new type called reference。

 So we load a reference from a local variable， and objects are always accessed in the spec via references。

 and the width of a reference is unspecified。 That's an implementation dependent features。

 So now we have things that are on the stack of unspecified width。

 In addition to the 32 and 64 bit things。This particular load takes the index of the variable it's going to load as the next byte in the bytecode stream。

And you can see it just pushes onto the stack。 The reference that came from that slot in the frame。

So the index is an unsigned byte。So indexes are in indexed by an 8 bit value here。

And into the current frame， it must contain a reference and。

The value is pushed onto the opera and stack。 And then there's this reference to wide further down for the case where 8 B is not enough。

 So， yes。I'm sorry。How long is a piece of string， They just picked a ba because that covers the common cases。

Well， you'll see when we get to wide， have they fixed that problem？um。The ear alert。

 here an interesting note。 The air load instruction cannot be used to load a value of type or return address from a local variable onto the operant tag。

 This air symmetry with the air store instruction is intentional。

 A little cryptic paragraph that is mystifying until you fit all the pieces of the puzzle together。

Okay， so here's wide。 wide is an instruction that modifies the next instruction。

And I can see all the hardware guys going， oh， no， no， please tell me you didn't。

So it extends the local variable index with additional bytes。

 So wide op code and Han now has two bytes， where op code is one of some other instruction。

 So it's a prefix that you add。And you add an extra byte as a suffix。 So now you have 16 bit。

Instructions。 And then you have another format for the I ink， which has not just an index byte。

 but a constant。 You remember， I ink， the increment。

 a local variable where you can have different constants and and wider indices。So yeah。

 hold your nose。我就。32。There may be a wide too。嗯。No， it just mentions wide there。

 Now there are hard upper bounds on the sizes of things。

 it may be that you can only have two to the 16 locals that might be the limit。

 If you look in the spec， you should be able to find that somewhere。

AnyDistruss that modify many distractions in the future？No， I don't think so。 Just one at a time。嗯。

Okay。So the wide op code is followed in the compile code by the op code of the instruction that it modifies。

 and then at the bottom。The embedded instruction must never be executed directly。

 its op code must never be the target of any control transfer instruction。

So that's one of the things that the verifier has to check when it loads your class file that you're not jumping into the middle of a wide instruction。

multiバイ。Yes， yeah。 in general， you always have to jump to the beginning of the instruction。

 And in this case， you， you know， you don't get to split hairs。Okay。Store。Is the converse of load。

 This one is the long store now we get that's a little funny because L store has an index and the index is the index into the local variable frame。

 but it's actually a pair of indices。N and N plus1 must be indices to the local variable array of the current frame。

And the value on the top of the upper end stack must be of type long and it's popped from the upper end stack and half of it goes into one of the local variables and the other half goes into the other local variable。

So we started with a description of a stack in which we had a stack of items of distinct sizes。

But we have now local variables that are of fixed sizes，32 B。

 because when we store something bigger than 32 bits。

 we have to nominate two variables adjacently to store them。

This is this schizophrenia pervaded the JVM spec from its inception， The original version。

 if you go back and pull like three versions back or further。

 it talked about the stack as a stack of 32 B quantities， mumble， except return addresses。

 which might not be 32 Bs， and the stack diagram for D add had two items。

Two pairs of items coming off the top of the stack and one pair going back on because a double is 2。

32 big quantities。 They decided for some reason in the spec that that was too confusing。

 and they rewrote it as a stack of。Small， you know， unique variable sized items。

 but it doesn't fit with the original bikecode definition， which stores。Multi， you know。

64 bit and larger quantities in multiple slots。 So this is like some weird historical anachronism and a strange piece of design。

 in my opinion。Because it's kind of it's sort of neither abstract nor concrete。You know。

 our local variables now we sort of saying they're really 32 bits。

But we needn't have done that in the design。Okay， so load。 that was the load of。嗯。

An item long gets sorry， the store into a local variable。

 So let's let's get something from the constant pool。 and we do that using LDC。

 And that is followed by an index， which is an index into the constant pool。

 You remember constant pool。 This big sort of soup of strings and structures and things。

 And that's how you get into it。 The index indexes the constant pool of the class containing the method that we're currently running。

 So there's a static way of finding it。 And he just pulls out the thing from the constant pool and sticks it on the top of the stack。

But it's not typed， right， This spike code can take an in or a float or a reference to a string literal。

Or a symbolic reference to a class and some other strange things。 And this one。

 they didn't choose to break it into the I L。Categorization， is is one by code that does。

 does it all。Interesting choice。ECorrect， because there is an LDC 2 for 64 B quantities。

So this works on all 32 B values and references of whatever size they are。Okay。

When would you want to learn a constant？Well， so for example， if you have a string in your program。

 a literal string， that will be in the constant pool and to get at it。

 you do an LDC with the index of the string， or if you have a number that can't be represented in one of the abbreviated op codes。

 you know，0， there are op codes for pushing like0 on1 and2 and minus-1 on the stack。

But if in your programme， you have the number 42。 Well， that's gonna be in the constant pool。

 And you have to get a hit by doing an LDC from the constant pool， yeah。M。Yes。台湾せ。

Pachine from the spring reference a 64 but you load value seat for the value seat。You bet。You back。

Okay。Here's another little paragraph， which is the tip of a very large iceberg。

 So if the runtime constant pool entry is a symbolic reference to a class。

 then the name class is resolved and a reference to the class object representing that class value is pushed onto the opera and stack。

 basically what this is saying is if the first time you mentioned if this is the first time you mentioned this class in that program。

Then the JVM， during the execution of this instruction has to go off， find the class， load it。

 passse it， build the internal structures that represent it。

 and then return your reference to that structure on the top of the stack。 So this。

 you know what in most cases is a simple， you know， instruction of a couple of， you know。

 when you compile it becomes two instruction or one instruction down this path。

 there's potentially millions of cycles being burned because you're loading stuff from the file system。

 maybe even over a network。 Okay， so there's there's a very big。

Amount of work implied by this one instruction in the case that it's the first time you resolve a class。

 And that， again， pervades the speck anywhere where you can mention a class。

 you'll find a paragraph that looks like this that says this is the first time you do it。

 You have to do all this work as well。 So that's not explicit in the bikecode that。 There isn't e。

 now resolve this class instruction。 It's， it's the first one to get there。 has to do it。Okay。

And we're doing 10 minutes。呃。Creating objects。The JVM doesn't say anything about where objects live in terms of addresses。

 address structure or even the layout of objects， have them represented in memory。

 but you do get to say when you want a new object and there are a handful of instructions that do that。

 The most common one is new which is used to create a new instance of a class and there are three flavors of instruction used to create arrays。

 there's array of things that aren't references， there's an array of things that are references。

 and then there's a thing to create multidimensional arrays。嗯。

You also have special instructions to access， you know。

 I said that the load and store actually only access the stack frame。

 If you want to access the fields of an object， use get field and put field。

 if you want to access the static variables of a class， you use get static and put static。

When you want to access a component of an array， you have typed instructions to access the array based on its types So there's B。

 C for char， S for something。 I is int， L long， etc cea。

 So there are loads from arrays of various flavors， a field of an array， a field， yeah。

And then you have corresponding stores for doing the stores to the arrays。

 and you have a special instruction to get the length of an array。

 It's not just a field and array object。 It's a special instruction。😊。

And then you have some type checking properties and stack management。 And we'll go through。 Well。

 we won't have time to go through all of these today。 But let's。

 let's look at least the new and maybe the， the field access。

So new is a fairly you know innocuous looking bycode， it has an index into the class pool。

 the class pool identifies a class that you're going to instantiate with a new object。

 you know and you have to go through the same rigmarural if the first time you've ever seen the class has to be resolved and loaded and all of that stuff。

嗯。So the memory is allocated out of the garbage collected heap。

 that's as much as it's going to tell you about the details of that mechanism。

 and then the instance variables of the new thing are initialized to the default initial values and there's a section that says what the default initial values of a Java object are basically numeric types are zero and reference types get initialized with null。

 which is a fairly nice same definition， but it does mean that this instruction。

 you know theres the amount of time it takes is dependent on the size of the object。

 And if you imagine extrapolating this two arrays where you'll see the same thing that applies。

 you know this bikecode has to zero out potentially all of an array before it returns a reference to it because there aren't you're not allowed to see aninitialized data in Java。

Can you think of why that might be， what would be a problem。

If you were to see the the uninitialized memory underlying an object。Louder security， Yeah。

 so security is one problem。 That's probably the most serious。 There's also garbage collection。

 which is there might be random bit stringings in there that look like pointers。Well。

It's because the model is designed to be able to download and run pieces of program in the context of a bigger program。

And those pieces are supposed to have limited access to the stuff around them。

And so if you were to be able to run a program and it would contain references to objects that you weren't supposed to be able to access。

 that would be bad。It's going to be clear it's references that are likely they're within the same JBN。

Well， they have to be in the same address spaceca， yeah， right。

 But you might be able to get access to things that you shouldn't be able to。

 because there's this whole security mechanism when you load stuff across the web。

Across the network about checking the structural properties。 And this were。

 if you could have an initialalized state， that could potentially bypass it。Okay。

 so here's the new array instruction。This is， yeah， another strange decision。 You know。

 we had these bycodes where the bycode op code distinguished the type。

 This one instead has a type code following。The op code and the type code detects one of these。

 these type values。 And that tells you what kind of array you're going to create。

 It's sort of part of the op code and sort of not。嗯。Notice that there isn't a reference type there。

There is this strange。Distinction in the， in the B variant。

 So if you notice the first one of these is T Booan。

And it says in A's Java virtualr machine implementation。

 arrays of type Booleion are storeded as a arrays of 8 bit values and are manipulated using the BA and BA store instructions which alter access a arrays of type byte。

So you get to choose whether booles are 8 Bs or 1 B in your implementation。

 But regardless of how you choose the same bikecode。

 the8 B of a flavor of bikecode is going to be used to access them because B A load and B S store are used to access。

By arrays and also Boolean arrays。I read that as。are minimum。No， no， it means you can。

 you can pack them if you want， but we're not gonna help you by giving you different instructions。

And I don't know where that word came from at the bottom。Okay。Yeah。

 let's just do get field and put put static so I mentioned there were accesses to objects and accesses to statics Get field is the thing that fetches the field from an object notice that the operaand is a index into the constant pool that index into the constant pool as a symbolic reference to a field and so it just names the field that you're going to pull from the object which you know if you interpreted this literally on every execution。

 every field axis would be really slow because you'd be doing string comparisons against some structure that you have for objects。

So you really don't want to do it literally as it has。

 but it does give you this freedom to implement the access and the layout in any way you like。

So fields are accessed by name that's the field of object access Stas are sort of like fields in classes。

 but they're not accessed as if there were fields and objects they' access using special bikecodes。

 get static and put static。😊，So this is put static， which sets the static field in the class。

 and it's the same kind of thing it uses a symbolic reference and the type。

Type of value must be compatible with the descriptor of the referenced field。 So in this case。

 we don't have the type information in the bike code。 The type information is in the descriptor。

 So that's another flavour of choice they've decided to take。Al right。

 I think we will stop there and we'll look at the。Rest of this， next week。It is just5 o'clock。

 any final questions or comments。Everybody clear about the assignments。So read。

 read the gozzling thing and implement the A S T interpreter。

And if you wantan to get ahead of the curve， do the bycode implementation。我呢定。

Why is the new for reference。