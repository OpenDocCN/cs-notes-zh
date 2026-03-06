# 【基于LLVM和MLIR构建编译器】 p18 How to build a compiler with LLVM and MLIR - 18 JIT Engine part 1 -BV1vi421Y7P1_p18-

Hello everyone， glad to have you back and welcome to another episode of How toBuild a Compr with LLBM and MOer。

In today's episode we're going to have a look at our implementation of Serin's Jeit engine like after a few episodes that we talked about Git and fundamentals of J。

 finally we're going to put everything together and have a working Git implementation。

It's going to take few episodes to talk about our implementation， even though it's bare minimum。

So to get things going， this current implementation， I named it Halley， named after Edmontaley。

 I needed a code name for this engine because in the future we might have more than one engine going we're going to run experiments on multiple implementations compare them together and basically we need to have。

Somehow we should be able to refer to different implementations， that's why I needed a code name。嗯。

Of course， this is not。Complete implementation， it's super， bare minimum。After all。

 it's the first stage of our compiler and we're looking to have a compiler all that is wired up and every piece work together with a minimum set of features。

 so don't expect anything fancy in this area but obviously in the future we're going to make improvements make it better and better。

It wraps LLG and L lasergit so it has two kind of operational modes we're going to use LLG whenever we need to actually。

Compil this stuff yearly， for example， whenever we pass the entire project in advance to our compiler and ask it to compile it。

 we're going to use the eager mode because like we know what we're going to compile in advance。

 but whenever we need to do some interaction with user like a raple mode or something like that。

 we're going to use the lazy kind of the lazy mode because it's going to。

Lower the latency and we're going to have a better interaction。

It uses on the object cache layer so whenever we compile a module to some object data。

 we're going to catch that data， so the next time we have to compile the same module we're not we're not going to actually compile it。

 we're going to use the same。Compiled object from before， and since LLVM modules are immutable。

 it works perfectly。And finally， our implementation at the moment supports adding ASDs and nameless spaces to the engine so we can add NAless spaces and ASDs to the engine and it's going to compile them and make the symbols available to us so we can look them up and invoke them。

So let's have a look at the actual implementation。In the source tree， we have a file called。

Hali doth as part of the header files， as you can see it's in the lip serene include directory and serin G highlyly doth。

嗯。It's going to take a little bit to compile everything。



![](img/41443cc609cfde8da0940c468d78d542_1.png)

![](img/41443cc609cfde8da0940c468d78d542_2.png)

First of all， some typeliaes。Maybe Jit and maybe GPTR just LLVM expected I don't know whether or not I can't remember if I talked about this but basically this type like expected type is part of the way LLVM handle like works with errors so basically here we say we expect to get like this maybe Git type is an like we expect a unique pointer to the Hallley type or an error right so that's how expected work works we're going to see it in action in a bit and maybe GtPTR or pointer is just like a function pointer and we wrap it in an expected type。



![](img/41443cc609cfde8da0940c468d78d542_4.png)

![](img/41443cc609cfde8da0940c468d78d542_5.png)

For the object cache layer， we actually inherit from LLVM's object cache and we need to actually overwrite just two functions。

 one is notify object compiled， which is like to populate the cache whenever we compile the module and we have the object buffer。

 we pass it to this function and it actually caches that buffer for us。



![](img/41443cc609cfde8da0940c468d78d542_7.png)

The buffer contains the compile data。And obviously a way to query the cache data。

 which is like get object， we give it the module that we want and it give it back a unique pointer to the memory buffer and like a handy thing to。



![](img/41443cc609cfde8da0940c468d78d542_9.png)

handy functions are you？To dump the object buffers to have files so we can actually debug things and it's useful for debugging and I'm going to talk about the dumping into the file in details in future videos because it's going to make this one longer and finally our storage in the object cache layer which is like a stream map a map from strings to。



![](img/41443cc609cfde8da0940c468d78d542_11.png)

Unique pointers of memory bufferuffs。And basically， that's where we cache the objects。AndFinally。Or。

Ero of the day are the Aliey class actually this is our GT engine， it wraps LLG。

 it has an attribute called engine， which is a unique pointer to LLG and sings a lazyG is a subclass of LLG。

 it works for both of them， but this implementation is not nice so。

If like we can't like by doing this， we can't actually use anything that El lazyGit has。

In addition to LG。It works for now and I'm not going to touch it because again bare minimum。

 we want bare minimum， but we need to create a new type that wraps these two types and we can decide which one to use actually。

But obviously i'm going to do that in the future and this is our cache layer。

 a unique point of our cache layer， I'm going to escape over these two G listener。

 which is for debugging for。Profiling， so we have another attribute called。

Did target machine be there？Or JTMB， basically it's a data structure that creates the target machine for us。

 the target machine， the details of the target machine that we want to generate code for。

a reference to data layout and obviously setting context it's everywhere and the shared pointer to a name a space。

As an active name aspace so basically whenever we use our jet engine we have an active name aspace we should be in some name aspace doing something this is how we track our execution flow we're going to have a look at it in the lecture in a bit and how it works and simple flag to。



![](img/41443cc609cfde8da0940c468d78d542_13.png)

actually indicate whether we're in the lazy mode or eager mode。



![](img/41443cc609cfde8da0940c468d78d542_15.png)

Our constructor is simple， get a context， the machine bill layer。

 the target machine layer and the data layout。But we're going to use this static function。Sorry。

We're going to use this aesthetic function to create create a instance of this create an instance。

 This is like this function would be the official way to create the。three or。

Another member function called set engine just to set the current engine that it's not a like a fancy one and look up function。

 this one is really important， this is how we actually this is how we can actually look into our compile code and look up symbols here actually。

The type of the input is symbol and it's like a expression symbol。

 not compile symbol actually since we have two names with two different meanings。

 I'm really looking like I'm not good at naming a stuff。And having two names， having a name。

 meaning two different things is really confusing， so I'm looking for a better name for。K， kind of。

The symbol name， the symbol in the context of compiled data， if you have any good suggestion。

 please comment down below。So we pass a symbol here because in a list we look up at stuff by a symbol right a symbol has a special evaluation rule so I'm going to show you the implementation in a bit I have some commented code here it's for my own reference I'm going to talk about them in the next episode but for now I'm not going to talk about them and I'm going to leave them in the source code I'm going to skip over packet function result that they're related to the next episode。



![](img/41443cc609cfde8da0940c468d78d542_17.png)

![](img/41443cc609cfde8da0940c468d78d542_18.png)

![](img/41443cc609cfde8da0940c468d78d542_19.png)

嗯。And finally， dump to object file， it's similar to the one from our cache layer we want。

To debug something， debug a compiled code and we want to have an object file that's where we use this function。

 add Ns and add ASD or kind of the interface functions for us to interact with our JT engine we add a name ofspace or an ASD to our we ask the Jit to add these two to the engine。

And finally， a getter function to get the active name and space。



![](img/41443cc609cfde8da0940c468d78d542_21.png)

Now let's have a look at how we actually。

![](img/41443cc609cfde8da0940c468d78d542_23.png)

Implement all this。

![](img/41443cc609cfde8da0940c468d78d542_25.png)

Obviously， we're in lip serin， Lib/je/hally。cppP。First of all。

 let's see how we can create a new instance of our jet engine。

So make haliit is the function to create a new instance based on a ser context。

 we pass the ser context in the ser context we have we have some configuration we can choose。

 for example， we create a。G target machine bill layer using the triple inside the CX inside the context。

 basically that triple right now points to the host machine so we can only run it for created for the host machine and then we call them a static function make in Haey past target bill layer。

 a target machine bill there and the steer context。

 obviously if there was an error return the error otherwise return。



![](img/41443cc609cfde8da0940c468d78d542_27.png)

The unique point。 So looking at this function。

![](img/41443cc609cfde8da0940c468d78d542_29.png)

It's a bit long。And like this is actually one of the most important parts first of all we have this target machine build there。

 we get the data layout for the target and stored it in the DL if there was an error return it that's how actually allerviium error expected works you can actually convert it to Boolean indicating that whether or not it contains an error right right now this if means if there was an error then take the error and return it and when you return an error it's like the expected value just it works in an like it's kind of a。



![](img/41443cc609cfde8da0940c468d78d542_31.png)

Acceptable value for an type。We create our G engine。

 like we call create a unique pointer passing the ser context and target B layer and the data layout。

 so G engine right now is created but we need to do more steps in order to actually use this one。



![](img/41443cc609cfde8da0940c468d78d542_33.png)

![](img/41443cc609cfde8da0940c468d78d542_34.png)

We created like a LLVM context， easy and nothing special about it。



![](img/41443cc609cfde8da0940c468d78d542_36.png)

We need an object linking layer， so if you remember from previous episode。

The way OrRC works is based on several layers working together。

 we pass the input data to the first layer， it does its magic。

 pass it to the second one and so on and so forth。嗯。



![](img/41443cc609cfde8da0940c468d78d542_38.png)

So basically this one is just a lambda that creates the object layer for us based on some of the settings we have or some of the default values。

 for example in here we use RT the like it's hard to pronounce it， but it's a just a。



![](img/41443cc609cfde8da0940c468d78d542_40.png)

Object linking layer and。

![](img/41443cc609cfde8da0940c468d78d542_42.png)

We use the section memory manager which is like one of the default memory managers in org。

 it's a simple one， it covers our needs for now we might end up needing a fancier section manager in the future。

 but for now it's fine。

![](img/41443cc609cfde8da0940c468d78d542_44.png)

Instead set up some handlers。Some windows related stuff。



![](img/41443cc609cfde8da0940c468d78d542_46.png)

And finally return the object layer， ignore all the commented code I have to clean the objects file I didn't have the chance I'm working on different places like different sections of the code at the moment again。

 we have another Lada that creates the compile function for us right This one is a straightforward as well we use a like IR compiler。



![](img/41443cc609cfde8da0940c468d78d542_48.png)

![](img/41443cc609cfde8da0940c468d78d542_49.png)

![](img/41443cc609cfde8da0940c468d78d542_50.png)

![](img/41443cc609cfde8da0940c468d78d542_51.png)

Layer to compile our code， we set the optimization layer based on the settings that we have in the ser context we get to like optimization level we can pass like 010203 things like that right now we saw that in like a episode that we talked about context ser context。



![](img/41443cc609cfde8da0940c468d78d542_53.png)

嗯。Then we create a target machine， we set the target machine。



![](img/41443cc609cfde8da0940c468d78d542_55.png)

um。Yep。And then here， if we're in the lazy mode， right， we create a different engine。

 we create a lazy jet engine， and if we're not， so this else is for LGt itself。

 So if we're in the lazy mode， we create a L lazyjiit。



![](img/41443cc609cfde8da0940c468d78d542_57.png)

passing the compiler function like the Lambda that we created to create a compiler layer and object layer and finally if we're not in the lazy mode。

 we just use LLG to create like a eager jet engine and we use set engine to set the created bulk engine as the current engine inside Halley。



![](img/41443cc609cfde8da0940c468d78d542_59.png)

嗯。And finally， this is not important。 This like an experiment I'm doing。



![](img/41443cc609cfde8da0940c468d78d542_61.png)

嗯。

![](img/41443cc609cfde8da0940c468d78d542_63.png)

Oh yeah， and finally we get the main Giitlib of our engine。

 we add the generator like our dynamic library search generator to our main Gitalib and at the end we return like the instance that we created from Hallli。

 we're going to talk about this in the future for now。



![](img/41443cc609cfde8da0940c468d78d542_65.png)

![](img/41443cc609cfde8da0940c468d78d542_66.png)

![](img/41443cc609cfde8da0940c468d78d542_67.png)

![](img/41443cc609cfde8da0940c468d78d542_68.png)

All you need to know is that like we successfully created jeting gene like an instance of Ha and really Turn。

Moving to other， there's like two other functions that are really important to us at ASD and where is it。

 our add name as space which is a little bit higher。



![](img/41443cc609cfde8da0940c468d78d542_70.png)

![](img/41443cc609cfde8da0940c468d78d542_71.png)

And let me find it， actually。

![](img/41443cc609cfde8da0940c468d78d542_73.png)

嗯。Here。So let's just start by add NS so what's happening is like it takes two parameters。

 the first one is a reference to the name of space。

 obviously we're going to add that name of space to our jet engine。Excuse me。

And the second parameter is just the location range。

 that location range refers to where do we actually try to include or import this name as space I didn't choose the terminology just yet。

So the way it works at the moment is that each name and space maps to one or more Gi diallips depends on the mode that we're in so if we're in a eager mode。

 it maps to just one Gi diallip because we have the source code of whatever we want to compile right but if we're in a lazy mode if we're interact trackinging with the user。

We don't have the entire sourcebook that we want to compile， so we get it little by from the user。

 so we have to create new Gi leavess based on whatever user might enter in the app。

That's why each name and space might have more than one Giit dial。

 so the way it works we create a new Gi dialli and we use the name like we format the name like this。

First， the name of the name of space and then。There are a number of that you daily that we want to include up。

We want to push to the context。 So， for example， if the name is user。

 the very first time that we're going to。嗯。Add that user name and space。

 we're going to have a Gi Li with with this name， user1。

 And then then second time we will end up with a new Gi Li called user 2 and So。



![](img/41443cc609cfde8da0940c468d78d542_75.png)

![](img/41443cc609cfde8da0940c468d78d542_76.png)

And if if we can't create the Giit title， just return an error， otherwise push it to the。Context。

So basically we say for this name and space at this cheatit title。

 I'm going to show you how how I implemented this one。And finally， compiled the name of space to。

With the machine code， like to the target code， better to say target code。

And if everything was the right， create a threadsafe module out of it。



![](img/41443cc609cfde8da0940c468d78d542_78.png)

And pack the function pack the function arguments I'm going to show you how it works。

 but in the future episode like in the next episode but for now it's safe to think that we're wrapping every function in our module in another function right with the same interface like this interface is the same for every function so whenever we look up steam balls we can actually。

Since we know the signature， we're going to invoke it easily。That's how we actually pack it stuff。

In the module and finally we're going to use add IR module， which is。



![](img/41443cc609cfde8da0940c468d78d542_80.png)

or member function in L Git or LL lazyG to add the newly created Gi leave with a a resulted measure right and return error success。

 which means yay， everything is good。

![](img/41443cc609cfde8da0940c468d78d542_82.png)

![](img/41443cc609cfde8da0940c468d78d542_83.png)

Same goes for。Oh， by the way。

![](img/41443cc609cfde8da0940c468d78d542_85.png)

You might might have noticed that we didn't do anything fancy about our symbols if you remember from our previous episodes when we talked about。

Creating a custom layer， we need to look up symbols。

 create like let the engine know that what symbols we actually compile。

 like what symbols this modules that we want to compile contains， right？

We're not doing that here because basically LLGt and LLLGit are doing that for us。

 we definitely have to do that in the future， but for now minimal set of features。嗯。

A ASD works the same like works the same way， actually in of a name and space。

 we have to only pass an ASD to it。And here's what activeN comes into picture so as I mentioned at any given time we're processing a nameless space。

 we're inside a name of space， everything that we're trying to evaluate is in the context of a name of space。

 a specific name of space so imagine we're in a rael and we type type in some list expressions。

And what happens is we use that add ASD function to add the ASD of the expression that we actually entered to our J engine and we look at our active NSs。

 what NSS are， what namelessspace we are in and we get the tree of that name ofspace。

 if you remember from the name ofspace episode， get three returns。

Victor of AST is basically or an ASD on its own。Of all the expressions that we have as part of that name and space。

We count the top level expressions， right， how many expressions do we have in that tree and ser offset？



![](img/41443cc609cfde8da0940c468d78d542_87.png)

And then we add that ASD into our active name and space， basically how it works I showed you already。

 it upends the ASD into the previous tree， so it kind of。

Like we were growing the tree with more ACs with more exps。



![](img/41443cc609cfde8da0940c468d78d542_89.png)

And if we had any error， just return the error or otherwise compile to LLVM from offset and we passed the offset here。

 we're like， okay， we compile whatever we had till now。

 add this Ac to your to the end name of space and then compile from。Where it starts in the vector。

 right， so we're going to just compile that newly added ASD。

We're going to do the same for a like the resulted module as well。

 we're going to create a threadSa module， it's going to be a threads save module we're not going to create a new one we're going to actually just start it in here some variable well and then run pack function arguments on that module which is going to actually walk through the functions and does it magic I'm going to show you in the next episode。



![](img/41443cc609cfde8da0940c468d78d542_91.png)

![](img/41443cc609cfde8da0940c468d78d542_92.png)

Then get the latest jitile loop for。The current name andspace， the active name andspace。

 so I'm going to show you in a bit， but this literally returns based on the number of the jit die lips。

 it returns the very last。G title that we added for that active Venice。It'sGoing to be a pointer。

 it should be there so that can't fail is a macro saying that yeah。It never fails。

 so it kind of ignores the error handling there。With the guarantee that it's not going to fail。

And finally， we're going to add that dial with that。

T save module into LGt or L lazyG and return success。

There's like I escaped so many details in here but。Again。

 I just wanted something to work with many minimum set of features。At this stage。

 we don't care about details。 we're going to get to them in the future。

 We just want something to work right the next step is how to look up a stuff in our。



![](img/41443cc609cfde8da0940c468d78d542_94.png)

![](img/41443cc609cfde8da0940c468d78d542_95.png)

认件。So we have a lookup function。Actually。Yeah let's talk about it in this episode really quick。

 we use get and S function from our context to get the name and space of the current symbol so。

Our symbol， like every symbol in has two values， one is the name and like embedded two values in it。

Like in itself， one is the name， which is like obviously the name of the symbol and the second one is N name。

 what name and space。Does that symbol refers to， So a symbol might in a least might be not every list。

 but in at least can be like。

![](img/41443cc609cfde8da0940c468d78d542_97.png)

不。

![](img/41443cc609cfde8da0940c468d78d542_99.png)

Bar right this full part here is the name ofspace。 It can be either a name is like a full name of a name ofspace or a name andspace a and the bar here is just a name of the symbol。

 So whenever we want to look up a symbol。 we pass like a compiled symbol。

 we pass a least symbol something like this to like a symbol expression to look up we choose like we use the Ns name to get the name ofspace from our context if there wasn't such a name of space obviously it's a bar it not it's not a bug。

 it's an error， we have to return an error。 Otherwise we get the latest dial for that name of space validate that it exists。



![](img/41443cc609cfde8da0940c468d78d542_101.png)

![](img/41443cc609cfde8da0940c468d78d542_102.png)

![](img/41443cc609cfde8da0940c468d78d542_103.png)

And then we use our engine to look up。

![](img/41443cc609cfde8da0940c468d78d542_105.png)

That name， that symbol name into our dial again， I'm going to talk to you about the make packed function name in the future。

 but since were wrapping the function， we need a better like another name for the function that is kind of the wrapper that actually create a function name。



![](img/41443cc609cfde8da0940c468d78d542_107.png)

And finally， again， validate it。Finally， if we can find anything， return an address to that。

Compiled symbol cast it to a function pointer because we already know we actually wrap everything in function。

So it must be a function， that's why we actually cast it to a function pointer。

And return the function pointer that's how we look up at stuff in our attention at the moment。

 I'm going to show you how to invoke them in future episodes because it's going to take much longer so。



![](img/41443cc609cfde8da0940c468d78d542_109.png)

![](img/41443cc609cfde8da0940c468d78d542_110.png)

For the Part one， that's it in the future episode we're going to have a look at other parts of our engine。

 especially around packing like functions in rapping functions in our module。



![](img/41443cc609cfde8da0940c468d78d542_112.png)

That's it for today， folks。If you like what I do， as always。

 please subscribe and leave a like it's going to help me a lot with this channel and hope to see you again。

 cheers。

![](img/41443cc609cfde8da0940c468d78d542_114.png)