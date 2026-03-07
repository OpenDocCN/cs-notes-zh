# 【基于LLVM和MLIR构建编译器】 p17 How to build a compiler with LLVM and MLIR - 17 Custom ORC Layers -BV1vi421Y7P1_p17-

Hey everyone， great to have you back， I hope you had fun with this video series so far。

In the last episode we talked about orrc layers， the basic plugs of any orrc based jet engine。

To build upon that discussion， we're going to talk about custom work layers today。

 we're going to learn how to create a layer to add or like any program representation to our GT engine。

Since the last episode， I finished the basic compiler w。For 17 episodes。

Our goal was to create a compiler with several critical components attached to each other and wired together to work with the basic and minimal set of features。

So I've done that now， we have different components like the J engine itself， SLIR， diagnostics。

 I don't know。Semantic analyzer， parser and other pieces。

All of them are now in place with basic functionality， they don't do much。

 for example the error handling system just prints out the error it doesn't do much like there's no traceback or anything and that's fine our aim was to just put them in place wire them together to have an idea of how they're going to work together to have the basic design。

就。I've done that。And。I decided to make some changes， some extra changes as well。

Just because in the future， anyone who wants to work on this compiler has to interact with L LVM project as well。

 especially the source tree。 I've decided to follow the same convention for the data for the sources structure of the G repository。

 so。I had to extract different programs that we have in the repository into dedicated directories in the root level。

 so I extracted lip serin， serin C， serin rep and other tools that we have and put them in the root directory exactly like how LLVM repository area。

Structured today。嗯。By doing that， I had to refactor the build system a little bit adding stock targets to every component separately。

Just because when we want to install the Ser compiler from source using CM。

 it would be like much cleaner and nicer like。Final installation would be much nicer and cleaner and also customizable anyone who wants to package this thing for different Linux distribution。

They would have like an easy time doing so。And finally。

 the way I work is usually I define some milestones for myself and when I reach any milestone after the milestone。

 I spend some time refactoring what I've done， reviewing everything documentation to make sure that they match the source code。

 I clean up the code that I might not need， sometimes a comment code in the repository just to as a reference for myself。

嗯。Also， I write some tests to pin down some of the functionalities and behaviors。

That's what I'm doing right now， and I'm going through all the twos that I have in the source code。

 make sure that either fix them or leave them for the future if they're like in a bigger scale。

So it's going to take a while before I can review everything and make sure that we're in good estate。

But the good thing is after I'm done with the refactoring。

 we're going to work on different components and focus on every component that we have。

You actually create the actual language now。For example， we're going to improve the JT engine。

 we're going to improve SLIR to actually reflect the different aspect of our language right now。

 we need the language specification to decide what we're going to do with this language we're going to decide on the type system。

We have a long journey basically ahead of us。Okay。That's it for the updates。

Going back to the topic of the day。Let's have a overview of what we discussed so far about our layers。

We know that jet engines like any org based jet engine is made out of layers。

 it holds a hierarchy of layers and those layers don't know about each other so layer a might only has a pointer or a reference to the。

Layer downstream of it right it doesn't know what it does like layer layer A doesn't know what layer B does。

 it just knows how to pass the result of any computation that it might have。To the layer B。

Layers basically wrap different type of program representation in a materialization unit。

Which those units get stored in jigile leaps。Basically any meization you need is responsible for describing different definitions that it wraps right。

 I'm going to show you in a bit how it works。And then pass those。Definitions to the layer。

Whenever matterization you need hand back the program representation to the layer。

It has like a materialization responsibility associated with it those responsibilities objects track the definitions and how to materialize them and there's a。

Like basically those responsibilities has a way to let the jitilelib nose when a certain symbol gets material。

 oh it's really hard for me to pronounce materialize， right？And deal with the errors。

We're going to have a look at how they work。We're going to create two materialization unit today。



![](img/c7f866b218336c088c7edc01b4426b8a_1.png)

So in order to create a custom layer， what we need is to first create a materialization unit to materialize whatever program representation that we might have。

Either ASDs or in our case name and spaces or if your language has byit codes。

 you might need like and you want to add byit code to your teaching gene。

 then you need a meization you need for your byte code and then。嗯。We need。

We need the layer class obviously the layer class is not anything special。

 you don't even have to inherit from another base class or anything like that。

 but conventionally layers have three main。Function members， add emit and get interface interface。

 It's up to you， up to you how to do like design it， but。It's good to follow the or conventionals。

Let's have a look at some code。Next， let me。Do it this way。So if we go to lip serene。L。Oh actually。

 include。7 it。

![](img/c7f866b218336c088c7edc01b4426b8a_3.png)

And live。Sorry。😔。

![](img/c7f866b218336c088c7edc01b4426b8a_5.png)

Thank you。So。We have two layers here， one to add NS any name and space to our J engine and another one to add ASDs to our g engine。



![](img/c7f866b218336c088c7edc01b4426b8a_7.png)

Let's start with the name of space one first， because it's。Much simpler。

 both of them are fairly simple， but name and space is even simpler。

If you remember from early episodes， we have a concept of name and space which。

Just contains a bunch of functions and symbols。 That's it。A file directly maps to a name ofspace。

 so each name of space has to have its own dedicated file or it can be in memory。

 it doesn't necessarily have to have a file， but you can't have like a name of space in two different files。



![](img/c7f866b218336c088c7edc01b4426b8a_9.png)

So first of all， we need a function called compile NS。

 which gets a name ofspace and spits out a TSafe module。



![](img/c7f866b218336c088c7edc01b4426b8a_11.png)

If you remember from or。EarEli episodes regarding to。Like OC design and everything。

 ORC has its own wrapper for the LVA module， which is called TreadSafe module。

 it just as the name suggests a TSafe module， we can work with it in a threadreadSa manners。

So this compiler this compile n function。

![](img/c7f866b218336c088c7edc01b4426b8a_13.png)

Just has like we can pass a name and space to it and it's going to compile it to LLVMIR。

So here's the。First of all， let's start with the layer insert， right， so here's the layer。



![](img/c7f866b218336c088c7edc01b4426b8a_15.png)

As you can see， we don't inherit from anything， it's just a regular C++ class。

We have a reference to ser context， the base layer is whatever layer is down a string to us。

 so what like the layer that is going to get or result like the result of this layer is going to be the input for the base layer。

 we have a reference to the man layerlia and the data layout。



![](img/c7f866b218336c088c7edc01b4426b8a_17.png)

So。In the constructor， we simply just get the value for those references。Initialize the object。

As I mentioned earlier， conventionally it's like the main function of any layer is the add function。

 so we can use that function to add different programme representation to our engine。In this case。

 our add function receives two parameters， the first one is a resource tracker and the second one is the name of the name ofspace。

The resource trackr， we've talked about this in the first GT episode。

It's just way to attract different resources that。Like。We put in it j dial， Right， So， for example。

 if we want like right now， when we compile。The namelessspace that we pass to add into LLVM orR and pass it to compile like to any other layer right eventually it's going to end up in memory in some format right and let's say we want to reload the name ofspace we want to add the name ofspace again to our J engine。

So。When we make sure that there's no reference to the old name and space definitions。

 so we can easily use this resource tracker to remove the code from memory。

 that's what a resource tracker does。So what's going on here is we seem like it's oh。

Forgot to mention that。Everything that I'm going to show you today is just an example。

I'm not using them in the actual jet engine of in just yet。Because we like。

Our aim was to create a simple compiler like bare minimum right we didn't we don't need any of that for the wiring that's why like I'm going to show you the actual implementation probably in the next episode or the next episode after that。

And you'll see that。Our jet engine is kind of much simpler than this。In the future。

 when we want to actually make improvement to our J engine， we're going to revisit this file。

 make some changes that make improve it in a way that is going to be suitable for us。

But now we're not using it， it's just an example。That's why we have some。

 we create some we create an unknown location location range and we pass it to the。



![](img/c7f866b218336c088c7edc01b4426b8a_19.png)

I function that receives location as well， so it's a polymer polymorphic function。



![](img/c7f866b218336c088c7edc01b4426b8a_21.png)

嗯。In this definition with three parameters， the location range is basically telling us that where we we're importing or where we're adding this name and space。

 for example， in context of pseudo do programming language when we import another name as space。

 this location would be pointing to that import expression or a statement depends on the language。

 right？

![](img/c7f866b218336c088c7edc01b4426b8a_23.png)

I'm going to show you the definition， actually， let me show it to you now。



![](img/c7f866b218336c088c7edc01b4426b8a_25.png)

So。We're just using a function from the context called Read name ofspace。

 all it does it is to find the file associated with that name of space name。In the file system。

Pass it like read it from the disk， pass it to the reader， get an ASD， run the semantic analyzer。

And if everything was right， create a name a space object and retain a， retain a result to。To us。



![](img/c7f866b218336c088c7edc01b4426b8a_27.png)

So if there wasn't， if there wasn't an error during this process， we simply returned the error。

 otherwise we're going to get。

![](img/c7f866b218336c088c7edc01b4426b8a_29.png)

Get the name of space and here's the important one part。



![](img/c7f866b218336c088c7edc01b4426b8a_31.png)

So。We're going to use the resource tracker that we have here right we get from the input。



![](img/c7f866b218336c088c7edc01b4426b8a_33.png)

So that resource track here is associated with a Git ti。



![](img/c7f866b218336c088c7edc01b4426b8a_35.png)

By Colen Gji。We're going to receive a like a reference to the Gta lab that this resource I care is made for。

 right？

![](img/c7f866b218336c088c7edc01b4426b8a_37.png)

So we can use the define function。Of any j leap to define new symbols in that j leap， right？

The defined function is like a polymorphic function。

 it has many different definitions with different input arguments。

 one of them that you can see right now receives a unique pointer to a materialization unit。



![](img/c7f866b218336c088c7edc01b4426b8a_39.png)

So here is what where actually meization units come to picture。Here we。

Like we have a materialization unit called NSS materialization unit。

 this unit here is responsible for materializing name and spaces。

We pass a reference to the current layer and the name and space that we just created。



![](img/c7f866b218336c088c7edc01b4426b8a_41.png)

Alongside with the oh， we pass these two to the constructor of that unit and then we pass that unit。

Alongside with the resource right here to the define function。



![](img/c7f866b218336c088c7edc01b4426b8a_43.png)

What happens is in this materialization unit we defined some symbol。You say， yeah， this。

Program representation， in our case， the name of space contains this list of symbols。

And we add those symbols back to our materialization unit。

 and then eventually we pass them to the define and define， add those symbols to our jit dial。

In this case， whenever we need any of those symbols， right， any of those symbols。

 just when we need them。The G engine knows that， okay。

 where to find those symbols in that Gi lip and。By passing the materialization unit。

 it knows how to materialize them。Since。We them， we're wrapping them right now in one unit。

When we look up any of those symbols， the entire unit gets compiled to and。

All other symbols would be accessible after that point as well。嗯。

I'm going to show you how like how did we define this thing？



![](img/c7f866b218336c088c7edc01b4426b8a_45.png)

嗯。So here's the。Unit itself it enrichs from materialization unit and basically when we define a new materialization unit we need to define two member functions。

 I like two important one actually three get name is the other one。

 but it's so simple just retain the name that said。



![](img/c7f866b218336c088c7edc01b4426b8a_47.png)

Constructor is totally up to us however we want we can create it。

 right now we receive like a reference to the NS layer itself and a reference to the name and space that we were going to actually materialize in the future。



![](img/c7f866b218336c088c7edc01b4426b8a_49.png)

嗯。The main function and the most important function here is materialize In this function。

 like we need to materialize the。Thing that we actually wrapping。Obviously。

 we're talking about the name and space right now。嗯。

This function gets a unique pointer to materialization responsibility， as I mentioned。

 theresponsibilities track what symbols needs to be materialized。



![](img/c7f866b218336c088c7edc01b4426b8a_51.png)

And the other important function is the discard function。This discard function。

 as you can see in the dark string， whenever we like we don't need a symbol anymore or we want to override a symbol。

 we need like this discard function is going to get called we need to handle any like like we need to discard symbols in this function。

For example， in case of a function， if we want to overwride a function。

 we have to get rid of the body of the previous one large。Or the arguments list or whatever。

 like clean up that function first it discarded， make sure that it's not accessible and replace it with a new one。

But since it was the wiring。Pace， I didn't do much here and to be honest。



![](img/c7f866b218336c088c7edc01b4426b8a_53.png)

I have to play around with this function as well。

![](img/c7f866b218336c088c7edc01b4426b8a_55.png)

And yeah， that's the materialization unit， it's super simple and the most important function is material realize if you look at the definition again。

 super simple。

![](img/c7f866b218336c088c7edc01b4426b8a_57.png)

![](img/c7f866b218336c088c7edc01b4426b8a_58.png)

Just calls the emit function of the layer itself and passes like。The responsibility and the Ns。

 like the name is based to that emit function。

![](img/c7f866b218336c088c7edc01b4426b8a_60.png)

So if you go back and look at the image function， so we receive the responsibility from the unit like the meization unit and a point a reference to the name of space that we want to materialize。



![](img/c7f866b218336c088c7edc01b4426b8a_62.png)

All we need to do。In this case， is to curl compile name and space on the Na of space。So。

As I mentioned earlier， the whole purpose of this compile in S is to compile a name andspace to LLVMR so what's going like right now we're passing an LLVMIR that is associated with our name andspace we compiles it to LLVMIR and pass it alongside with a materialization responsibility to the layer down a stream to us。

 so this thing in here。This thing in here is actually the result of our process。

 the result of our layer。We pass our the result of our layer to alongside with that responsibility to the base layer to whatever is down a stream to us and accepts our output as an input in this case that would be a like compiler layer that compise L LVM2 object code。



![](img/c7f866b218336c088c7edc01b4426b8a_64.png)

There's one other member function which is really important in order to show you how it works。

 first I need to show you how to use the like。And S layer in the jet engine itself， so。



![](img/c7f866b218336c088c7edc01b4426b8a_66.png)

If we have a look at engine dot H。

![](img/c7f866b218336c088c7edc01b4426b8a_68.png)

![](img/c7f866b218336c088c7edc01b4426b8a_69.png)

First of all， we have two members for NS layer and ASC layer。

 I'm going to show you AS layer in a bit。

![](img/c7f866b218336c088c7edc01b4426b8a_71.png)

When we actually in our。

![](img/c7f866b218336c088c7edc01b4426b8a_73.png)

Constructor of our engine Oh， by the way， this engine is not the actual engine as well。

 it's just an example engine I wrote to play around with it。



![](img/c7f866b218336c088c7edc01b4426b8a_75.png)

![](img/c7f866b218336c088c7edc01b4426b8a_76.png)

The actual engine， I'm going to talk about it in future episodes。



![](img/c7f866b218336c088c7edc01b4426b8a_78.png)

But。We saw something like this in the last episode when we actually went through some of the examples from Lerviium itself。

So we have different layers， object layer and compiler layer， transformer layer。

 transform layer we saw how to actually。Create any of those in the previous episodes。



![](img/c7f866b218336c088c7edc01b4426b8a_80.png)

So here we create two new。To牛。Layers we actually initialize our layers that we added to our engine。

The N layer and layers， both of them。Have transformed layer as the pattern。

 so not pattern like downstream layer。So right now we have like a tree like hierarchy。

 we have NS layer and AST layer as su to each other and they both have transform layer as the downstream and transform layer has compile layer as its downstream and finally compile layer compiler layer result goes to the object layer。



![](img/c7f866b218336c088c7edc01b4426b8a_82.png)

![](img/c7f866b218336c088c7edc01b4426b8a_83.png)

So when we actually。呃。Iitialize this thing。In this layer， we pass a reference to the ser context。

Pace layer， manr and data layer。

![](img/c7f866b218336c088c7edc01b4426b8a_85.png)

We saw that earlier， right。Sorry。

![](img/c7f866b218336c088c7edc01b4426b8a_87.png)

We saw that here。But let's look at how we actually manage it。うんうんうん。



![](img/c7f866b218336c088c7edc01b4426b8a_89.png)

Sorry， oh， I made a mistake， sorry。

![](img/c7f866b218336c088c7edc01b4426b8a_91.png)

In the constructor of our materialization unit， whenever we create the materialization unit in add function。

 right？

![](img/c7f866b218336c088c7edc01b4426b8a_93.png)

![](img/c7f866b218336c088c7edc01b4426b8a_94.png)

Here。Whereium come drillers over here。

![](img/c7f866b218336c088c7edc01b4426b8a_96.png)

We call this constructor here right， if we look at the constructor。

 we see that we get a reference to the layer and the name and space， right？



![](img/c7f866b218336c088c7edc01b4426b8a_98.png)

![](img/c7f866b218336c088c7edc01b4426b8a_99.png)

![](img/c7f866b218336c088c7edc01b4426b8a_100.png)

And we need to pass。Like we need to call the meization unit constructor because we inherit from it。

 And you know， when we call that we。First invoke the get interface function of the layer passing the name and space to it。

 and then pass the result， which is an interface to the meization unit。



![](img/c7f866b218336c088c7edc01b4426b8a_102.png)

So what's going on in this function？So what happens here is that like we define what symbols this meization unit contains。

 right？

![](img/c7f866b218336c088c7edc01b4426b8a_104.png)

![](img/c7f866b218336c088c7edc01b4426b8a_105.png)

In case of a name and space， we easily can traverse the ASC tree and find all the definitions and create a symbol from it so that's what we're doing here at the moment。

We have a table called like a map called symbols， it's just a normal map。We。

Look into our environment， like if you remember from early episodes like every name of space has an environment attached to it that keeps track of the global variable global definitions and bindings。

 so we traverse that environment and we get the name of any expression。

 root level expression and the expression itself， then we look at the type whether it's a function or if it's a function。

 we set the flags to be call level。

![](img/c7f866b218336c088c7edc01b4426b8a_107.png)

![](img/c7f866b218336c088c7edc01b4426b8a_108.png)

Alongside me being exported。I'm going to talk about the flags in the future。

 but for now exported uncolable mean a they describe a function。

 functions that are callable and exported from other places as well。嗯。But because the definition。

 we just want the symbol name， the definition is going to be provided later。

And we use the manr to mangle the name。And add that。Symbol to our symbol map， right。

 that's how we do it here。

![](img/c7f866b218336c088c7edc01b4426b8a_110.png)

So we put the mand name in our symbols map that we defined。



![](img/c7f866b218336c088c7edc01b4426b8a_112.png)

At the beginning of the function。 and finally。We assigned a list of flags to that mand name。

When we oh and we return an interface containing those symbols。By doing this。

 the G will know that what symbols are available to it from that materialization unit。

 So whenever we look up any of the symbols that we actually。



![](img/c7f866b218336c088c7edc01b4426b8a_114.png)

Create here we insert into our symbols map here。The Giitdi will know which materialization you need to use and it's going to call the materialized function of that materialization you need to basically convert that program representation in our case name and space to LLVMIR and pass it to the transform layer for us。



![](img/c7f866b218336c088c7edc01b4426b8a_116.png)

That's how it works and to show you another example。



![](img/c7f866b218336c088c7edc01b4426b8a_118.png)

嗯。We can have a look at the ASCS stuff as well or to add ASCs directly to our jetT engine。



![](img/c7f866b218336c088c7edc01b4426b8a_120.png)

![](img/c7f866b218336c088c7edc01b4426b8a_121.png)

It works the same so we have a function called compile ASD that instead of compiling a name ofspace。

 it receives like a name ofspace and an ASD and compiles that ASD in context of that name ofspace This ASDN name ofspace is really specific to serene if you're working on any other language that doesn't have name ofspaces you just can compile any ASD to LVMIR code。



![](img/c7f866b218336c088c7edc01b4426b8a_123.png)

And we have the meization unit here， it works similar to the previous one， get name and again。

 we don't care about the discard， it holds a reference to name and space。

 the AST layer and the ASD itself， it will look at the materialize。



![](img/c7f866b218336c088c7edc01b4426b8a_125.png)

![](img/c7f866b218336c088c7edc01b4426b8a_126.png)

We'll see that it again， calls the emit function of the AS C layer。

 but it this time it passes the responsibility alongside name and based on AS SD。



![](img/c7f866b218336c088c7edc01b4426b8a_128.png)

And here's the gas still layer itself quite simple， holds a reference to the parent layer。

 down the stream layer， sorry， reference to the man layer。



![](img/c7f866b218336c088c7edc01b4426b8a_130.png)

![](img/c7f866b218336c088c7edc01b4426b8a_131.png)

![](img/c7f866b218336c088c7edc01b4426b8a_132.png)

Again， same routine is quite similar to the previous layer， the add function。



![](img/c7f866b218336c088c7edc01b4426b8a_134.png)

Creates the materialization unit with the the input study it accepts and called the defined function of the J dial loop。



![](img/c7f866b218336c088c7edc01b4426b8a_136.png)

The emit is against similar compiles that ASD using the compile ASD function into LLVMIR and pass that one with a materialization responsibility to the emit function of the downstream layer。



![](img/c7f866b218336c088c7edc01b4426b8a_138.png)

![](img/c7f866b218336c088c7edc01b4426b8a_139.png)

And get interfaceface again is the same but conceptually is the same。

 but the way it works is different， just looking into the AST to figure out what symbols it exports and like what key binding it makes。

 sorry not key binding， name binding it makes and basically creates a symbol for them。

 add them to the symbol map and finally return on interface。



![](img/c7f866b218336c088c7edc01b4426b8a_141.png)

![](img/c7f866b218336c088c7edc01b4426b8a_142.png)

![](img/c7f866b218336c088c7edc01b4426b8a_143.png)

嗯。So it's quite easy to understand like the layer， the conceptual of layer is really。

Brilliant because it's so abstract and so simple that makes like a really complicated thing like a jetT engine so easy to understand。



![](img/c7f866b218336c088c7edc01b4426b8a_145.png)

To show you how compile NSS works in our case， our name aspace exposes a function called compile to LLVM that we saw it earlier。

 that one just reads the ASD， walk the ASD calls the generate function on different nodes to come up with the LLVMIR and finally added to a L LLVM module。



![](img/c7f866b218336c088c7edc01b4426b8a_147.png)

The compile ASD works the same with a few with a small difference。

 the difference is like we get the tree of the name and space because we want to。



![](img/c7f866b218336c088c7edc01b4426b8a_149.png)

Compilile that ASD in the context of the given name and space。We add， we。Add the。

We need to add the ASD to the name and space so that ASD will end up being a part of that name and space and there's another function in the name ofspace which is compiled to LLVM from offset it's like we add that ASD to our name and space and basically ASD itself like the tree that the name and space has。

 it's just the vector of ASDs right so we say like we ask the compiler to compile the tree from the given offset like from the exact location that we added the ASD to so it would be like compile only the ASD but with respect to the rest of the context it can look up symbols in the environment from previous ASDs。



![](img/c7f866b218336c088c7edc01b4426b8a_151.png)

![](img/c7f866b218336c088c7edc01b4426b8a_152.png)

Like that's the only difference we compile Ns。

![](img/c7f866b218336c088c7edc01b4426b8a_154.png)

。So。As you can see， creating all layers or custom layers are quite simple。嗯。

We don't need them right now the like in the first milestone in the first phase。

 but I have a feeling that in the future going to we need to create our own。啊。

or layers as well with the same purpose add name and spaces。

 add As or add Bte codes codes to the JT engine or add shared libraries or whatever like there's like tons of stuff that you can do with the libraries with the layers。

There's like other layers built like made from the。U。buuilt in into Org like the compiler layers。

 the what was the jitlink layers， it's a really good idea to have a look at them。

To like to read the code， they're great examples if you want to start creating your own custom layer。

In the next episode or the one after that I'm going to show you the actual implementation of stain jet engine which is kind of really basic。

 I've decided to keep it basic and only implement what we need and later on we can。

Enhance it or improve it in any way that we need。I guess that's it for today。

I'm really excited about this video series， I hope you're having fun with it。

I'm looking forward for all your feedback and if you like what I'm doing。

 please subscribe subscribe to the channel and leave a like it's going to help me quite a lot。

Thank you， thanks for。Listening and see you in the next episode。



![](img/c7f866b218336c088c7edc01b4426b8a_156.png)