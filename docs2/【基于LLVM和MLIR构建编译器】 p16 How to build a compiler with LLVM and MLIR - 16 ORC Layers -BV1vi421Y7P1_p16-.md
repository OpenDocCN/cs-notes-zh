# 【基于LLVM和MLIR构建编译器】 p16 How to build a compiler with LLVM and MLIR - 16 ORC Layers -BV1vi421Y7P1_p16-

Hey friends， great to have you back and welcome to episode number 16。Since the previous two episodes。

 we started our adventure into the GitW in episode number 14。

 we had a discussion over what is the Git， how just in time compileil works and some of the highle concepts and in episode 15 we talked about LLBM related Git concepts like OrRC。

 MCG， some terminologies， like the highle API of org， like how to use LLG and LLAGit。

 and two major solutions to implement our own GT Engine。So。

We continue our journey in episode 16 as well， but we're going to have a deeper dive into the org design。

 like always some updates。In the past three weeks， I guess three weeks。

 I was working on the Giitta as usual， I tried to add the support for add the ASD support to the engine and it went well。

Right now， our engine accepts some ASD form compile it into the target code and make it available for invocation。

But working on that made me realize that okay， I might like our SLIR is basics， of course。

 but I still might need some big changes into the I need to make big changes to the SLIR so I went back I started changing stuff and very soon I realized that okay。

Our error handling system is really on my nerve and I have to fix it。Up until now， after 16 episode。

 I always tried to postpone the like postpone working on the error anything error related to the future as the last piece of the compiler wiring。

But yeah it's really on my nerve I have to I had to fix it basically we had two different classes of errors one was like LLVM related errors。

 whatever LLVM provides and I had my own。Like design for certain errors。Both were fine。

 but they kind of couldn't coexist， right？So I was like， yeah， I can't take it anymore。

 let's unify them， let's just have one error handling system or that just works， right？

So I started to actually refactor ser errors to act as LLVM errors， it's not that hard。

 it's actually really easy， LLVM provides enough documentation around errors for us to use them。

 but the problem was the way I want my errors to be I need so many of them。

Uon like before this episode I used to have like I used to create the error messages manually in like a CPP file and use them wherever I need to。

 but like it was really ridiculous to do that like it took me a lot of time so I was like okay I know about tablegen。

I knew that I have to use tablein at some stage。Today is the day， let's figure it out。

I looked at the table Gen documentation， I created my own instance like Ser instance of the table gen to generate errors for me。

 I created back and for the errors， so right now we can actually create our errors in like a nice descriptive way in like ODSS style。

File and basically pass it to the our own table gen in senseense and it it creates it creates。

Nice CPP file with all the errors slides。In it， it is night it works I still have didn't finish it completely yet。

 I need to make some adjustments， but'm on I'm on track。After doing this。

 I'm going to go back working on the LIR。Make some changes and finally finish the ASD support to digit。

 like the basic ASD support to digit。But。Enough of updates。Let's see what's the plan for today。

Excuse me。As I mentioned， we had a brief look at LLGit and L laserGit。

 the two Giit engines that LLVM provides out of the box。

 but in order to use them and to understand them better we need to have a better understanding of each component that make up that makes up those two engines。

And in order to understand components better， we need to start from layers。

 what is layers and what are layers and how can we use them？In today's episode。

 we're going to specifically look at how to use layers。

 but in the future episode we're going to define our own layers and look at the details of layer definition in the future。

But what are layers？Basically in orque design。Layers are the basic block of an engine。So。

We can create a Jit engine by having several other layers connected to each other and like working in like a certain way。

 we can think of them as like a data pipeline because at the end of the day， each layer。

Get some something in a like a different format。 it's it might be either an AD or LLVM I or。

 or I don't know some。Compilation result or whatever and transform that data into another form。

And layers are kind of are composable， like kinda because。They have orders。

 we have to compose them in an order that makes sense and each layer has some requirements on its own and it has its own details。

 their interface might not even be the same but the important thing here is that the order of layers matters。

The way we chain them together basically dictates their requirements。Sorry。

 the requirements dictates how we actually chain them together。Each layer in orrc design。

 each layer holds a reference to the next layer or the down stream layer。嗯。If。Actually不。So。

We can actually really like。To have a。Kind of a graph to demonstrate how layers work org。

Like we can have something like this， right， there's a hierarchy of layers in the GitT engine。

Depens the depends on our goal， the number of layers might be different。

 the layers themselves might be different。So right now we have a jet engine and two input types。

 input type A， input type B， for example， input type A can be like ASDs input type B can be。

Object box directly， right？Layer A add the support for input type A to our J gene and layer B adds the support for an input type B。

So we can submit like a value of input type B， sorry a into our g engine using the layer A。

 and we can do the same for layer input type B and layer B。

 but both of layer A and B have the same parent。Layer C。

 so when we submit something to the jet engine that has the input type A。

 layer A will take care of that， transform that input type into something that layer C expects。

And layer B does the same thing for input type B so at the end of the day layer C will accept just one input type and accepts only one input type it receives that input type makes some transformations to it pass it to layer D layer D does the same and pass it to layer E and finally layer E comps it to a target code or to another。

Even to something else， it doesn't have to be target code just put target code there because it's relevant to us。

And make it available for like lookups in vocation and stuff like that， right？That's how layers。

 like as you can see， like layer itself is a concept and it's like a really abstract concept。

We don't know what each layer does， we can actually define different layers with different goals。

To see them in action， we're going to have a look at the kidoscope sheetit。Ter of today。So。

Vium examples。这是。Let's go。jeit。Chapter  one。So。嗯。In the previous episode we talked about LLG and L laserigitt。

 right， the engines， those two engines that LLVM provides out of the box。

 but in Klyos like we don't use them right， we create our own engine that is kind of the same like our engines serves the same purpose as the LLG。

So understanding this really simple engine helps us understand Lit better right。

 so we start by creating a like a class called Coscoje。

We hold a unique pointer to the execution session if you remember execution session represent a running Jit。

We have a data layout， a man glare that mand the name of the symbols in memory， we have two layers。

Right we have an object layer and a compile layer， these two layers are provided by LLBM already。

 we don't have to be worried about that object layer is an object linking layer and compile layer is an IR compile layer。

Basically。Sorry， compiler is our compiler。Excuse me。

 compile layer is our compiler and object layer is our kind of link here we have just one j loop。

This is like， here's the interesting part that。Actually， we create our chain of layers。一。

First of all， we create the execution session， we move the execution session that we pass to the constructor to ES。

 same we do the same for the data layout and we create a new manr。

Based on the data layout and the execution session。Here's the pump part。

We define a new object layer by calling the constructor on the。Oject link layer。

 object linking layer passing the execution session and conquer and sorry passing the execution session and the Lambda that create creates a unique pointer to a memory management if you remember about like if you remember from the previous episode we talked about this like memory managers are just a tool that manages memory for us like allocations the allocations and stuff like that LVM provided the section memory manager which is like a really simple memory memory manager most of the time it would be fine for our use cases and we used it here today by we I mean like whoever wrote this tutorial。

We're not going to be worried about this thing yet。Just yet。

 but I even didn't create anything new for Sere Jt。

 we're going to look at this our own implementation of Jit in the future。

 but I'm using the same memory manager for now， but I'm pretty sure we're going to like we have to create our own memory manager in the future as。

But for now。The object linking layers just needs a Lambda to create like that to create a memory manager right。

 and we use the section memory manager as our default memory manager。So， we have the。

We have the object layer， which is the most like it's the end layer in our data pipeline。

We have only two layers， but we can say that object layer is kind of the target layer for us if it makes sense and compile it。

Sorry。And compile layer is kind of our first layer。

To create the compile layer we called the constructor of IR compile layer by passing the execution session and the downstream layer right or downstream layer would be。

Object layer， that's why we pass it here。So。On paper compile layer doesn't know what exact layer is down a stream to it。

 It just knows it holds a reference to something， some sort of a layer。

 and it knows that whenever it compiles anything， it has to pass the result of that compilation to that down a stream layer。

 So on paper， we should be able to add a like a。I don't know， a third layer here。Whatever layer。

 right， let's call it。Layer。A， and have about that girl。Different layer here。

Then we can actually construct that layer by passing some stuff here like。Again。

 we might need the execution session and。

![](img/12859cfa60d41d283f9069690d11684d_1.png)

Object layer as our downstream layer。

![](img/12859cfa60d41d283f9069690d11684d_3.png)

And then。Sorry。Then instead of object layer here， we can pass a。

 so then we're going to have3 who I forgot to。Actually use so in instead of having just two layers we we introduce a new layer in between compile layer an object layer that does something for us what does it do we don't know because like it's an app like it just made it on the fly but。

My point is。Like compile layer doesn't have to know what exact layer is coming after it。

 it just need to know what layer to pass the compilation result， right？So， going back。🎼嗯。Yeah。So。

Here we have the compiler layer。And we tell it to pass whatever you compile to the object layer。

And then we need to pass a compiler to it like right now in this tutorial。

 we're using the concurrent Ir compiler， which is like a moodly threaded compiler。

There's like a simple compiler as well， which is like single threaded， we can use that one as well。

 but it's not the topic of discussion for today we can have a look at it in the future time。Finally。

 we create our main Giit lab by creating a new pair jit lab called Ma like these two greater and these two。

Sorry， I'm lost a little bit， so we're calling it main， but those two greater signs are just。呃。

There we can literally call it name like this or whatever name we want， right？

There's no requirement to do that。And we add a dynamic generator to our main jet dial what is the generator will look at it in the future。

And finally，We make sure that whenever we like in our distract。

 we make sure to end the session and the cheat session and if anything bad happened， just report the。

So we have a static method called create to actually create an instance of Klyosscriptje。

 we create like execution process control， we're going to have a look at it in the future。

 what is it and what it does。If there was an error， take the error and return it。

 otherwise create an execution session using that execute process control and then create a J target machine builder with the target TriL and everything。

Create the sorry data layout and finally call the constructor of Kidoscopejeit and return a unique pointer。

 Nothing is special。We have some like a couple of。Gets for getting like the JT and data layout and finally the most important member function at measure。

So compileiling layer accepts。LLVMIR module2 like as an input。So a modules have two inputs。

 a threadSa module that we talked about it in the previous episode is just a wrapper around the normal LLVM module that makes it thread safe and the resource tracker。

I guess we talked about resource trackers in the previous episode as well。

The purpose of a resource tracker is to keep track of the resources that we allocate。

 right we can use the resource tracker to remove them。So。if， since it's an optional argument。

 if there wasn't any。Resource tracker pass to our function。

 we just get the default resource tracker for our main J loop。

And then we call the member function add of our Comp layer。

Passing the resource structureer and moving there。Tread safe modules to it。This is how actually am。

Wevo a layer as we're going to see in the future when we want to define our own layer。

 we have to create an add member function that。Thatcepts the input of that layer， basically。

And finally， return any possible error that it might return。

The lookup member function is straightforward， just look up whatever symbol that we have。

 like the name of the symbol that we get into the main Gilib and of course man the name and then look it up in the execution session。

So this is it because the compiler layer is already defined in LLVM and provided by the LLVM we don't link we don't look into the details of it because。

I'm going to show you in the future how to define a layer and it's kind of more relevant to that discussion。

So going back to our kind of a slides， I don't know what to call this one。嗯。

We have something like this， you know right now we saw something like this。

 we have just one input type which is LVMIR module， we have two layers。

 compile layer or compiler layer and object layer。The input of like compiler layer。

 compile layer actually accepts。Any form of L L VMIR module or a F F safe module。It comp it to some。

 like。I don't know， it comps it to some target code and pass it to object layer and object layer just links stuff based on some rules together。

Kind of provide the target code for us The object layer on its own doesn't provide the target code。

 but the arrow here I try to demonstrate that after object layer we have some target code ready to work with。

 we can look up symbols in it， we can like invoke any symbol and stuff like that it doesn't the target like object layer doesn't probe create anything special for us。

 it just links that stuff together。I'm going to talk about symbol resolution and stuff like that in the future。

 and at that time it would make more sense。And let's have a look at。The second example on chapter 2。

So。Most of the code is the same as before but we added another layer。

 so we created another layer called optimizeized layer which is an IR transform layer again this layer is provided by LLVM we don't look into how it works we're going to use it only。

So if you look at the constructor， object layer is our final layer。

 compile layer seats just before it and optimize layer seats in front。

 like it would be the first layer in our pipeline。It gets just it gets the execution session and they like a reference to the next layer。

 which in this case is compile layer， the compile layer。

 again as I mentioned earlier it can be any other layer as long as the output of optimized layer makes sense for that layer doesn't have to be compile layer。

 but since our design is like optimize layer compile layer and link layer。

 that's why it sits in front。And finally， it gets like a function to optimize a module I'm going to show you how it works and the rest are the rest is the same。

Only in the add module member function this time instead of calling the compile layer。

 we call optimize layer because optimized layer is now the front layer for us。

 the layer that is the start of our pipeline。We call the app member function like before we pass the resource tracker and the thread save module。

Look up is the same and here's the function that we pass to the optimized layer。It takes。

Tt module and the materialization responsibility end this word。And。I guess I showed you this already。

 but module has a。ThrereadSave module has a member function called with Mo do that accepts a Lambda that accepts a Lambda。

 that Lambda gets the LLVMIR module that wrapped inside the threadSafe module as an argument and inside this Lambda we can work with that LLVM module in its threadSafe manners。

What we're going to do here is to create a pass manager， apply some passes to the module。

 run the pass manager and。Finally， move the thread safe module out。So what happens here is that。

In the previous example， when we pass the LLVM module to the compile layer。

 it just compiles it into some target code， pass it to the object layer。

 but what if we want to do we want to run some passes some optimization on our LLVM module。Easy。

 we create a new layer， we pass the LA module to that one。

 it takes care of all the pest management and stuff like that as you can see right now and。

The input for this module is a。LLVM module， the output is just another LLVM module。

 not just another LLVM module， it's the same LLVA modules module but with some passess applied to it。

 and then we can pass it to the compile layer。But if we， if we have a look at。哦。

How we use it actually。So。Can search for。It in the。So let's go oops， sorry。やま。

Here is how we define a J like not be。The author defined the J， a unique pointer to the kidoscopeje。

And in a shell I module， we use the same data layout that our Gi has to set the data layout of the module。

And。Yeah， whenever we actually。Whenever we want to handle any definition in kidoscope。

 you have to read the Kidoscope code to like understand this kind of stuff like how the ASD works and stuff like that。

 but it's kind of obvious if the definition was a function ASD and stuff like that。

 we need to do this。As you can see， we call the add module and pass a LLVM module to it。

 so add module is like the interface of our G engine to the art side world。嗯。

One thing that is really。Interesting， I want you to see is this block of've code here。

So the function name is handle top level expressions in this toy language。

 whenever we write something in the top level of our module。

 I guess this function is going to get called to handle that expression。What happens is。

We get the default resource tracker of our。Main Giilelib so we have only one。

 if you remember we had only one jIlib in our engine。

 we create a resource rack for that JitTlib and name it RC。

 then we have a module that like we compile the expression we have to like an LLVM module， right？

Basically that's what a compiler frontend does right， we talked about it。

Previous episodes and it's not important right now。

 what is important is that this TSM here contains an LLVM， like a threadsSafe LLVM module right now。

And we pass it to amale。To be added to our GT engine by calling a module passing the moving the TSM into it and passing the resource tracker。

 we add our LLVA module to our GT engine so from the outside world by doing this that like that LLVM module we know that it's going to be compiled into target code and be available to us as long as there's no error messages that exit on error will just。

top the execution if something bad happens。As soon as we actually added our module to our engine。

 we called new like initialized module to create set up a new module again。

 that's not important for us， and this is like what is really important to us。We look up。

Something called。I like a non expert or anonymous expression， right？This name is here is what。

The author of this code chose to name this like。Symbol that we have in the。

LLVM module IR module right this is something up to you to decide they've decided to use this name right you can pretty much use whatever you like based on your rules they chose to use this right so they wrapped their anonymous expression into in a function and they name that function an anonymous expression that's why we look up this symbol here。

So what's happening here is that。We have an expression on our top level expression。

 we wrap it into a function called anonymous expression compile to LLVM or modulejo。

Add that module to our J engine and by then we kind of expect that like our engine compiles it to the target code。

 some target code and make it available for us to interact with。

And we can look it up if everything goes right， we're going to have a symbol with the same name that we can look it up and invoke it so we're looking it up。

 we get like a reference to it。A pointer to it， sorry， as you can see。

 the same variable here has the type sheet evaluated symbol we had a look at this type in the previous episode。

And we just cast it to a function pointer because we like in this tutorial we know we only support doubles and stuff like that。

 we know the signature like in an actual word well we don't know we might not know the signature and we have to figure it out in some way but right now it's a fixed signature。

 we know we know the signature that that's why we use this kind of function pointer。

 we get to address to that team， cast it to a function pointer。

 put it in FP and finally call FP and print out the result right here's the interesting point。Before。

Before we kind of before the handle top level expression ends， we call resource tracker remove。

Why is that？So。As you can see here， we always look up the same symbol if we invoke this function many times we're going to look up the same symbol over and over again。

But。What happens if we have a symbol， we have the symbol already and define the same symbol again。

 right it's going to pay like we can't redefine a symbol by that like ourG engine doesn't support that。

So what's happening here is whenever we see a top level expression in our code。

 we compile it to LLVMIR， added it to our G， we give it the same name all the time。

We look it up we invoke the function pointer， quite ca it to function pointer and invoke it and make sure to remove that function that resource tracker tracks the function。

 tracks the IR sorry LLVM IR module that we add to RG right。We're like， okay。

 here is a module I want to compile to the target code， we hand it to the G and we say。

 here is the resource tracker I want to associate these two together。

Whenever we're done with the vocational interaction with our target code。

 we just call remove on this resource track here to make sure that G gets rid of that definition that target code for us after our here remove from the outside world we would be like okay that code doesn't exist anymore so there there wouldn't be any anonymous expression anymore we can actually use the redefine this symbol again。

That's why we call remove and it's really important to do this because we don't want to our G doesn't support redefining a symbol。

 right？So going back to our slides。Actually， if I want to show you。呃。

An overview of what we talked about for chapter two。Allrry。Chapter 2， this would be 3。要直前。

So we added another layer。Called the。What was itim layer。嗯。I。Lei。Right。

That optimized layer was our like input。 So a from node A， we would go to D and stuff to B on here。

From the。To。Bi。Oh， sorry。Let's name this to E this here。Okay， let me generate this one really quick。

Oh yeah， as you can see。We don't care how we get like an LLVM module because it's not the topic of the discussion for today。

 we talked about it already， we know how to like generate LLVM modules。

 but when we when we end up with an LLVM module we know in our second example we have three layers The first one is the new layer optimize layer we pass the LVmiR to it it applies some passes to it and generate not it doesn't generate it applies some passes to it and pass the same LLVM module to the compile layer compiler layer expects some LLVMR module and then compiles it to the target code pass it to object link layer to take care of the linkage and then make it available to us So as you can see layers are the basic block of any J engine in orV2 I really like this design I'm really impressed with the design it's so easy。

Follow so easy to understand。Easy to extend scalable， I'm loving it。And。As we。

 as I'm going to show you in the period in the。Future episodes。

 it's really easy to actually define a layer so layers can be anything they like we can create create layers to kind of look inside our data pipeline as a like a tap layer or we can add layers to add support for ASDs that that's what I did。

 we can add layers to。I don't know。Basically， add white codes， whatever。

 like it's up to you and whatever goal you have。You can use layers to achieve your goal。

 you create a pipeline based on your layers， LLVM layers。

 and get whatever you want out of your jet engine。So。I guess that's it for today， folks。

Playyers are quite nice like this design is quite nice， I really enjoyed using it。

 I hope you find them useful as well。Please share your feedback with me about the whole video series。

 and if you like what I do， if you enjoyed the video series， either this one or the one about Emax。

 please consider subscribe to the channel and leave a like。 It would help me quite a lot。嗯。

And that's it。Enjoy your day and see you in the future episodes。



![](img/12859cfa60d41d283f9069690d11684d_5.png)

Cheers。